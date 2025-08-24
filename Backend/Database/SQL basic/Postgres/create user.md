To create a PostgreSQL user (role) with **full access** (ALL privileges) to a **specific database**, follow these steps:

---

### 🧰 1. Access PostgreSQL

Log in to the `psql` shell as the `postgres` superuser:

```bash
sudo -u postgres psql
```

---

### 🧑‍💻 2. Create the User (Role)

```sql
CREATE USER myuser WITH PASSWORD 'mypassword';
```

Replace `myuser` and `mypassword` with your desired username and password.

---

### 🗄️ 3. Grant All Privileges on a Specific Database

Assuming your database is named `mydatabase`:

```sql
GRANT ALL PRIVILEGES ON DATABASE mydatabase TO myuser;
```

This gives the user permission to connect and do anything **within that database**.

---

### 🔧 4. (Optional) Grant Access to Existing Tables & Future Tables

If the database already has tables, grant privileges on them:

```sql
\c mydatabase  -- Switch to your database
GRANT ALL PRIVILEGES ON ALL TABLES IN SCHEMA public TO myuser;
GRANT ALL PRIVILEGES ON ALL SEQUENCES IN SCHEMA public TO myuser;
```

To make sure the user has privileges on **new tables created in the future**, run:

```sql
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON TABLES TO myuser;
ALTER DEFAULT PRIVILEGES IN SCHEMA public GRANT ALL ON SEQUENCES TO myuser;
```

---

### ✅ Done!

Now `myuser` has full access to `mydatabase` (but not to other databases).

Let me know if you want this user to also create new databases or be a superuser.

``` sql
-- Replace with your desired username, password, and database name

CREATE USER userpg WITH PASSWORD 'pgAdmin';

  

CREATE DATABASE mydatabase OWNER userpg;

  

GRANT ALL PRIVILEGES ON DATABASE mydatabase TO userpg;

  

-- Optional: make the user a superuser

ALTER USER userpg WITH SUPERUSER;
```