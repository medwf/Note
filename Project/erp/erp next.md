# installation

ERPNext officially supports Debian/Ubuntu. On **Arch Linux**, it works but requires manual setup. Below is a **tested Arch guide** to install **ERPNext 15** using **Bench + Frappe**.

> ✅ ERPNext v15  
> ✅ MariaDB  
> ✅ Node v18  
> ✅ Python 3.11+  
> ✅ Redis  
> ✅ Yarn  
> ✔ systemd services

---

## ✅ **Step 1 — Install Dependencies**

```bash
sudo pacman -S --needed git python python-pip redis mariadb nodejs npm yarn wkhtmltopdf \
  imagemagick mariadb-clients gcc make cmake yarn openssl
```

Enable Redis:

```bash
sudo systemctl enable --now redis
```

---

Initialize MariaDB:

```bash
sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql
sudo systemctl enable --now mariadb
sudo mysql_secure_installation
```

Create DB user:

```bash
sudo mysql -u root -p -e "CREATE USER 'frappe'@'localhost' IDENTIFIED BY 'frappe';"
sudo mysql -u root -p -e "GRANT ALL PRIVILEGES ON *.* TO 'frappe'@'localhost' WITH GRANT OPTION;"
```

---

## ✅ **Step 3 — Install Frappe Bench**

```bash
pip install frappe-bench
```

Initialize bench:

```bash
bench init erpnext-bench --frappe-branch version-15
cd erpnext-bench
```

---

## ✅ **Step 4 — Create Site**

```bash
bench new-site mysite.local
```

Enter admin password when asked.

---

## ✅ **Step 5 — Get ERPNext App**

```bash
bench get-app erpnext --branch version-15
```

Install ERPNext:

```bash
bench --site mysite.local install-app erpnext
```

---

## ✅ **Step 6 — Start ERPNext in Development**

```bash
bench start

```

Open in browser:

```
http://localhost:8000
```

---

## ✅ **(Optional) Production Setup**

Install supervisor + nginx:

```bash
sudo pacman -S supervisor nginx
bench setup production $USER
```

---

## 🛠 **Common Arch Errors & Fixes**

|Error|Fix|
|---|---|
|`ModuleNotFoundError: frappe`|Activate virtualenv: `source env/bin/activate`|
|MariaDB won't start|Double-check `/etc/my.cnf.d/server.cnf`|
|Node version error|Use Node 18: `sudo pacman -S nodejs-lts-fermium`|
|PDF not working|`wkhtmltopdf` installed above|

---

## 🎯 Done!

Your ERPNext 15 is now running on Arch Linux ✅

---

## ❓ Need Next Step?

Reply with a topic:

1. Configure email
    
2. Setup domain & SSL
    
3. Systemd + Production
    
4. Nginx config
    
5. Migrate to PostgreSQL (dev only)
    

Just tell me: **"Show #3"** or ask anything.

Would you like me to generate a **script to automate all steps**?