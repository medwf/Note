
# problem found with mariadb
## Initial file data 
- `sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql`
- `sudo mariadb-secure-installation`

## Problem using sudo to connect via mariadb
``` sh
sudo su 
mariadb

> SELECT User, Host, plugin FROM mysql.user WHERE User='root';
> ALTER USER 'root'@'localhost' IDENTIFIED BY 'YourStr0ngPassword';
> EXIT;
```

