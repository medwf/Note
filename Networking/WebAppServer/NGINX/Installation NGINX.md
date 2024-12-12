To install Nginx on Ubuntu, you can use the package manager, `apt`. Here are the steps:

1. Open a terminal on your Ubuntu machine.

2. Update the package list to make sure you have the latest information about available packages:
``` shell
sudo apt update
sudo apt install nginx
sudo systemctl status nginx
sudo service nginx status
```
If Nginx is running, you should see an "active (running)" status.

6. Open a web browser and enter your server's IP address or domain name. You should see the default Nginx welcome page, indicating that Nginx has been successfully installed.

That's it! You have successfully installed Nginx on your Ubuntu machine. You can now start configuring it according to your needs, such as serving web pages or setting up reverse proxy configurations.

The main configuration file for Nginx is usually located at :

-  /etc/nginx/nginx.conf,

And server-specific configurations can be added in the

- /etc/nginx/sites-available/ directory.