# What is PHP ? 
- A **popular general-purpose scripting language** that is especially suited to web development. Fast, flexible and pragmatic, PHP powers everything from your blog to the most popular websites in the world.
- PHP is a server scripting language, and a powerful tool for making dynamic and interactive Web pages.
- PHP is a widely-used, free, and efficient alternative to competitors such as Microsoft's ASP.
- PHP is an acronym for "PHP: Hypertext Preprocessor"
- PHP is a widely-used, open source scripting language
- PHP scripts are executed on the server
- PHP is free to download and use.

# Set Up PHP on Your Own PC
However, if your server does not support PHP, you must:
- install a web server
- install PHP
- install a database, such as MySQL
### install web server.
#### using Apache.
```shell
sudo apt update
sudo apt install

# Install PHP along with the Apache PHP module:
sudo apt install php libapache2-mod-php

# Some php models.
sudo apt install php-cli php-cgi php-mysql php-pgsql

# ckeck version of php
php -v

# restart apache
sudo systemctl restart apache2

# php setup
# create file.
sudo nano /var/www/html/info.php

# add following context to file.
<?php
phpinfo();
?>


```
#### using nginx.
``` shell

```