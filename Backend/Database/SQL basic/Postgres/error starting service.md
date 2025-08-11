The error you're seeing means that PostgreSQL hasn't been **initialized yet**—its data directory (`/var/lib/postgres/data`) is missing or empty, so the service can't start.

To fix this, you need to **initialize the PostgreSQL data directory** manually using the `initdb` command.

### ✅ Fix Steps

Run the following command **as root or with sudo**:

```bash
su -l postgres -c "initdb --locale=C.UTF-8 --encoding=UTF8 -D '/var/lib/postgres/data'"
```

Or if you're using `sudo` (preferred for most users):

```bash
sudo -u postgres initdb --locale=C.UTF-8 --encoding=UTF8 -D /var/lib/postgres/data
```

### 📌 What this does:

- `initdb` creates the initial database cluster in `/var/lib/postgres/data`
    
- `--locale` and `--encoding` set the default character settings
    

### 🔄 Then start PostgreSQL:

Once initialized, start the service again:

```bash
sudo systemctl start postgresql
```

And to enable it at boot:

```bash
sudo systemctl enable postgresql
```

Let me know if you want to use a different data directory or have custom configuration needs.