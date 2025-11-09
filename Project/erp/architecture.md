Perfect choice ✅ — **ERPNext** is one of the most developer-friendly and truly open-source ERPs out there.  
Let’s go step-by-step:

---

## 🧠 ERPNext Architecture Overview

ERPNext is built on the **Frappe Framework**, a full-stack web framework written in **Python** and **JavaScript**.

Here’s the structure:

```sh
 ┌──────────────────────────────┐
 │        Web Browser (UI)      │
 │  React / Vue / JS + Jinja    │
 └──────────────┬───────────────┘
                │
 ┌──────────────▼───────────────┐
 │      Frappe Framework        │
 │  (Python + REST API layer)   │
 │ - Handles routing, models,   │
 │   views, forms, permissions  │
 │ - Provides REST / GraphQL API│
 │ - Event system, background jobs│
 └──────────────┬───────────────┘
                │
 ┌──────────────▼───────────────┐
 │        ERPNext App           │
 │  Business logic & modules:   │
 │  Accounting, HR, CRM, etc.   │
 └──────────────┬───────────────┘
                │
 ┌──────────────▼───────────────┐
 │        Database Layer        │
 │     MariaDB (or MySQL)       │
 └──────────────────────────────┘
```

- **Backend:** Python (Frappe)
    
- **Frontend:** JavaScript (React/Vue + Jinja templates)
    
- **Database:** MariaDB
    
- **Web Server:** Nginx (reverse proxy)
    
- **Background tasks:** Redis + Celery-like queue
    
- **Bench CLI:** Developer tool to manage apps, sites, and processes
    

So, ERPNext = Frappe Framework + ERPNext App.

---

## ⚙️ Local Installation (Development Setup)

### 🧩 Requirements

|Dependency|Version / Note|
|---|---|
|OS|Linux (Ubuntu 22.04 recommended) or WSL on Windows|
|Python|3.10+|
|Node.js|18+|
|Yarn|1.22+|
|MariaDB|10.6+|
|Redis|latest|
|wkhtmltopdf|for PDF printing|
|npm, git, curl|standard tools|

---

### 🪄 Installation Steps (Developer Mode)

#### 1️⃣ Install Dependencies

```bash
sudo apt update
sudo apt install git python3-dev python3-pip python3-venv mariadb-server redis-server \
nodejs npm yarn wkhtmltopdf curl
```

#### 2️⃣ Setup Database

```bash
sudo mysql_secure_installation
sudo mysql -u root -p
```

Then inside the MariaDB shell:

```sql
CREATE USER 'frappe'@'localhost' IDENTIFIED BY 'frappe';
GRANT ALL PRIVILEGES ON *.* TO 'frappe'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

#### 3️⃣ Install Bench CLI

Bench is the management tool for Frappe apps:

```bash
pip install frappe-bench
```

#### 4️⃣ Create a new Frappe bench environment

```bash
bench init erpnext-bench --frappe-branch version-15
cd erpnext-bench
```

#### 5️⃣ Get ERPNext app

```bash
bench get-app erpnext --branch version-15
```

#### 6️⃣ Create a new site

```bash
bench new-site mysite.localhost
# Set admin password when prompted
```

#### 7️⃣ Install ERPNext on the site

```bash
bench --site mysite.localhost install-app erpnext
```

#### 8️⃣ Start the server

```bash
bench start
```

Then open your browser at:  
👉 **[http://localhost:8000](http://localhost:8000/)**

---

## 🧩 Folder Structure

Inside your `erpnext-bench` directory:

```
erpnext-bench/
├── apps/
│   ├── erpnext/        ← Business modules
│   └── frappe/         ← Core framework
├── sites/
│   ├── mysite.localhost/
│   │   ├── site_config.json
│   │   ├── private/
│   │   └── public/
└── Procfile / logs / env / etc.
```

You can create new modules using:

```bash
bench new-app my_custom_app
bench --site mysite.localhost install-app my_custom_app
```

---

## 🧠 How Customization Works

|Type|How to Customize|Example|
|---|---|---|
|**UI / Forms**|Use Frappe Desk → Customize Form|Add custom field in "Sales Invoice"|
|**Backend Logic**|Add hooks & Python classes|Trigger logic before saving a document|
|**Frontend (JS)**|Add JS file per Doctype|`public/js/custom.js`|
|**New Modules**|Create a new Frappe App|`bench new-app inventory_plus`|

---

Would you like me to give you the **Docker setup version** (easier for quick local testing, no dependency mess) or you prefer the **manual developer install** (for coding directly)?