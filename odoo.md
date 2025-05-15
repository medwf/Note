I understand the issue now. When your Odoo container runs with root privileges but you're working as a normal user on your host system, you encounter permission problems when trying to create or modify files in the custom-addons directory. This is a common Docker permission issue. Let me provide a complete solution.

## Solution for Permission Issues Between Docker and Host

There are a few approaches to solve this. I'll provide you with the most straightforward solution using the right Docker setup:

### Option 1: Run the container with your host user's UID/GID

This is the most reliable method for development environments.

1. First, create a revised Dockerfile (save as `Dockerfile.dev`):

```dockerfile
FROM ubuntu:noble

SHELL ["/bin/bash", "-xo", "pipefail", "-c"]

# Generate locale C.UTF-8 for postgres and general locale data
ENV LANG en_US.UTF-8

# Retrieve the target architecture to install the correct wkhtmltopdf package
ARG TARGETARCH
# Arguments for user setup
ARG USER_UID=1000
ARG USER_GID=1000

# Install some deps, lessc and less-plugin-clean-css, and wkhtmltopdf
RUN apt-get update && \
  DEBIAN_FRONTEND=noninteractive \
  apt-get install -y --no-install-recommends \
  ca-certificates \
  curl \
  dirmngr \
  fonts-noto-cjk \
  gnupg \
  libssl-dev \
  node-less \
  npm \
  python3-magic \
  python3-num2words \
  python3-odf \
  python3-pdfminer \
  python3-pip \
  python3-phonenumbers \
  python3-pyldap \
  python3-qrcode \
  python3-renderpm \
  python3-setuptools \
  python3-slugify \
  python3-vobject \
  python3-watchdog \
  python3-xlrd \
  python3-xlwt \
  xz-utils && \
  if [ -z "${TARGETARCH}" ]; then \
  TARGETARCH="$(dpkg --print-architecture)"; \
  fi; \
  WKHTMLTOPDF_ARCH=${TARGETARCH} && \
  case ${TARGETARCH} in \
  "amd64") WKHTMLTOPDF_ARCH=amd64 && WKHTMLTOPDF_SHA=967390a759707337b46d1c02452e2bb6b2dc6d59  ;; \
  "arm64")  WKHTMLTOPDF_SHA=90f6e69896d51ef77339d3f3a20f8582bdf496cc  ;; \
  "ppc64le" | "ppc64el") WKHTMLTOPDF_ARCH=ppc64el && WKHTMLTOPDF_SHA=5312d7d34a25b321282929df82e3574319aed25c  ;; \
  esac \
  && curl -o wkhtmltox.deb -sSL https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6.1-3/wkhtmltox_0.12.6.1-3.jammy_${WKHTMLTOPDF_ARCH}.deb \
  && echo ${WKHTMLTOPDF_SHA} wkhtmltox.deb | sha1sum -c - \
  && apt-get install -y --no-install-recommends ./wkhtmltox.deb \
  && rm -rf /var/lib/apt/lists/* wkhtmltox.deb

# install latest postgresql-client
RUN echo 'deb http://apt.postgresql.org/pub/repos/apt/ noble-pgdg main' > /etc/apt/sources.list.d/pgdg.list \
  && GNUPGHOME="$(mktemp -d)" \
  && export GNUPGHOME \
  && repokey='B97B0AFCAA1A47F044F244A07FCC7D46ACCC4CF8' \
  && gpg --batch --keyserver keyserver.ubuntu.com --recv-keys "${repokey}" \
  && gpg --batch --armor --export "${repokey}" > /etc/apt/trusted.gpg.d/pgdg.gpg.asc \
  && gpgconf --kill all \
  && rm -rf "$GNUPGHOME" \
  && apt-get update  \
  && apt-get install --no-install-recommends -y postgresql-client sudo \
  && rm -f /etc/apt/sources.list.d/pgdg.list \
  && rm -rf /var/lib/apt/lists/*

# Install rtlcss (on Debian buster)
RUN npm install -g rtlcss

# Install Odoo
ENV ODOO_VERSION 18.0
ARG ODOO_RELEASE=20250428
ARG ODOO_SHA=952a8f7148a7652809546ee7acdc2d66c09e04d9
RUN curl -o odoo.deb -sSL http://nightly.odoo.com/${ODOO_VERSION}/nightly/deb/odoo_${ODOO_VERSION}.${ODOO_RELEASE}_all.deb \
  && echo "${ODOO_SHA} odoo.deb" | sha1sum -c - \
  && apt-get update \
  && apt-get -y install --no-install-recommends ./odoo.deb \
  && rm -rf /var/lib/apt/lists/* odoo.deb

# Copy entrypoint script and Odoo configuration file
COPY ./entrypoint.sh /
COPY ./odoo.conf /etc/odoo/

# Create a new user with the same UID/GID as the host user
RUN usermod -u $USER_UID odoo && groupmod -g $USER_GID odoo && \
    # Give odoo user sudo permissions without password
    echo "odoo ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/odoo

# Set up directories with proper ownership
RUN mkdir -p /var/lib/odoo /mnt/extra-addons && \
    chown -R odoo:odoo /var/lib/odoo /etc/odoo /mnt/extra-addons /entrypoint.sh && \
    chmod 755 /entrypoint.sh

VOLUME ["/var/lib/odoo", "/mnt/extra-addons"]

# Expose Odoo services
EXPOSE 8069 8071 8072

# Set the default config file
ENV ODOO_RC /etc/odoo/odoo.conf

COPY wait-for-psql.py /usr/local/bin/wait-for-psql.py
RUN chmod +x /usr/local/bin/wait-for-psql.py

# Use odoo user that matches host UID/GID
USER odoo

ENTRYPOINT ["/entrypoint.sh"]
CMD ["odoo"]
```

2. Create a new development-specific docker-compose.yml:

```yaml
version: '3'
services:
  db:
    image: postgres:15
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=odoo
      - POSTGRES_USER=odoo
      - PGDATA=/var/lib/postgresql/data/pgdata
    volumes:
      - odoo-db-data:/var/lib/postgresql/data/pgdata
    
  odoo-dev:
    build:
      context: .
      dockerfile: Dockerfile.dev
      args:
        USER_UID: ${HOST_UID:-1000}
        USER_GID: ${HOST_GID:-1000}
    depends_on:
      - db
    ports:
      - "8069:8069"
      - "8071:8071"
      - "8072:8072"
    volumes:
      - odoo-data:/var/lib/odoo
      - ./custom-addons:/mnt/extra-addons
    environment:
      - HOST=db
      - PORT=5432
      - DB_USER=odoo
      - DB_PASSWORD=odoo

volumes:
  odoo-db-data:
  odoo-data:
```

3. Create a shell script to run the container with your current user's UID/GID:

```bash
#!/bin/bash

# Save this as run-dev.sh
export HOST_UID=$(id -u)
export HOST_GID=$(id -g)

docker-compose -f docker-compose.yml build
docker-compose -f docker-compose.yml up -d
```

4. Make it executable:

```bash
chmod +x run-dev.sh
```

5. Run your development environment:

```bash
./run-dev.sh
```

### Option 2: Using a Volume with the Right Permissions

If you prefer not to rebuild the container:

1. Create a script that sets up the correct permissions before starting:

```bash
#!/bin/bash

# Save as setup-permissions.sh
ADDONS_DIR="./custom-addons"

# Create the directory if it doesn't exist
mkdir -p "$ADDONS_DIR"

# Set ownership to match Docker's odoo user (usually UID 101)
sudo chown -R 101:101 "$ADDONS_DIR"

# Set permissions to allow group write access
chmod -R 775 "$ADDONS_DIR"

# Add your user to the odoo group
# This assumes Docker is creating a group with GID 101
if ! grep -q "^odoo-group:" /etc/group; then
    sudo groupadd -g 101 odoo-group
fi

# Add current user to the odoo group
sudo usermod -a -G odoo-group $(whoami)

echo "Please log out and log back in for group changes to take effect"
```

2. Make it executable:

```bash
chmod +x setup-permissions.sh
```

3. Run the script:

```bash
./setup-permissions.sh
```

4. Log out and log back in for the group changes to take effect. Then you can start your containers as normal.

### Option 3: Create a Development Script for File Creation

If you just need to create files inside the container:

```bash
#!/bin/bash

# Save as create-module.sh
MODULE_NAME=$1

if [ -z "$MODULE_NAME" ]; then
  echo "Usage: $0 module_name"
  exit 1
fi

# Create module structure
docker exec -u odoo odoo mkdir -p /mnt/extra-addons/$MODULE_NAME/{models,views,security,static/description}

# Create base files
docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/__init__.py" << 'EOF'
from . import models
EOF

docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/__manifest__.py" << EOF
{
    'name': '${MODULE_NAME^}',
    'version': '1.0',
    'summary': 'Custom module',
    'description': """
        Custom module created for Odoo 18.0
    """,
    'category': 'Uncategorized',
    'author': 'Your Name',
    'website': 'https://yourwebsite.com',
    'depends': ['base'],
    'data': [
        'security/ir.model.access.csv',
        'views/views.xml',
    ],
    'demo': [],
    'installable': True,
    'application': True,
    'auto_install': False,
}
EOF

docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/models/__init__.py" << 'EOF'
from . import models
EOF

docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/models/models.py" << EOF
from odoo import models, fields, api

class ${MODULE_NAME//_/}(models.Model):
    _name = '${MODULE_NAME}.model'
    _description = '${MODULE_NAME^} Model'

    name = fields.Char(string='Name', required=True)
    description = fields.Text(string='Description')
    active = fields.Boolean(string='Active', default=True)
EOF

docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/security/ir.model.access.csv" << EOF
id,name,model_id:id,group_id:id,perm_read,perm_write,perm_create,perm_unlink
access_${MODULE_NAME}_model,${MODULE_NAME}.model,model_${MODULE_NAME//./_}_model,base.group_user,1,1,1,1
EOF

docker exec -u odoo odoo bash -c "cat > /mnt/extra-addons/$MODULE_NAME/views/views.xml" << EOF
<?xml version="1.0" encoding="utf-8"?>
<odoo>
    <data>
        <!-- Form View -->
        <record id="view_${MODULE_NAME}_form" model="ir.ui.view">
            <field name="name">${MODULE_NAME}.form</field>
            <field name="model">${MODULE_NAME}.model</field>
            <field name="arch" type="xml">
                <form>
                    <sheet>
                        <group>
                            <field name="name"/>
                            <field name="description"/>
                            <field name="active"/>
                        </group>
                    </sheet>
                </form>
            </field>
        </record>

        <!-- Tree View -->
        <record id="view_${MODULE_NAME}_tree" model="ir.ui.view">
            <field name="name">${MODULE_NAME}.tree</field>
            <field name="model">${MODULE_NAME}.model</field>
            <field name="arch" type="xml">
                <tree>
                    <field name="name"/>
                    <field name="active"/>
                </tree>
            </field>
        </record>

        <!-- Action -->
        <record id="action_${MODULE_NAME}" model="ir.actions.act_window">
            <field name="name">${MODULE_NAME^}</field>
            <field name="res_model">${MODULE_NAME}.model</field>
            <field name="view_mode">tree,form</field>
        </record>

        <!-- Menu -->
        <menuitem id="menu_${MODULE_NAME}_root" name="${MODULE_NAME^}" sequence="10"/>
        <menuitem id="menu_${MODULE_NAME}" name="${MODULE_NAME^}" parent="menu_${MODULE_NAME}_root" action="action_${MODULE_NAME}" sequence="1"/>
    </data>
</odoo>
EOF

# Create an empty icon file
docker exec -u odoo odoo mkdir -p /mnt/extra-addons/$MODULE_NAME/static/description/
docker exec -u odoo odoo bash -c "touch /mnt/extra-addons/$MODULE_NAME/static/description/icon.png"

echo "Module $MODULE_NAME created successfully!"
```

Make the script executable:

```bash
chmod +x create-module.sh
```

Use the script to create a new module:

```bash
./create-module.sh my_custom_module
```

## Recommended Approach: Development Container Configuration

For the best development experience, I recommend using option 1 with an additional enhancement. This approach uses Docker's user namespace remapping to solve permission issues permanently:

1. Create a file called `.env` in the same directory as your docker-compose.yml:

```
HOST_UID=1000
HOST_GID=1000
```

2. Update these values with your actual UID/GID:

```bash
echo "HOST_UID=$(id -u)" > .env
echo "HOST_GID=$(id -g)" >> .env
```

3. Create a specific docker-compose.dev.yml for development:

```yaml
version: '3'
services:
  db:
    image: postgres:15
    environment:
      - POSTGRES_DB=postgres
      - POSTGRES_PASSWORD=odoo
      - POSTGRES_USER=odoo
      - PGDATA=/var/lib/postgresql/data/pgdata
    volumes:
      - odoo-db-data:/var/lib/postgresql/data/pgdata
    
  odoo:
    build:
      context: .
      dockerfile: Dockerfile.dev
      args:
        USER_UID: ${HOST_UID:-1000}
        USER_GID: ${HOST_GID:-1000}
    depends_on:
      - db
    ports:
      - "8069:8069"
      - "8071:8071"
      - "8072:8072"
    volumes:
      - odoo-data:/var/lib/odoo
      - ./custom-addons:/mnt/extra-addons
    environment:
      - HOST=db
      - PORT=5432
      - DB_USER=odoo
      - DB_PASSWORD=odoo
    command: ["odoo", "--dev=all"]  # Run in development mode

volumes:
  odoo-db-data:
  odoo-data:
```

4. Run your development environment:

```bash
docker-compose -f docker-compose.dev.yml up -d
```

With this setup, you'll be able to create files in your custom-addons directory with your normal user permissions, and they'll be accessible inside the container with the proper permissions.

This is a complete solution that gives you proper file permissions and an easy development workflow. When you're ready to go to production, you can still use your original Dockerfile without these modifications.