Certbot HAProxy | Setup Tutorial

by [Shahalamol R](https://bobcares.com/blog/author/shahalamol-r/) | Jan 31, 2023

Read the article to find out the method to secure HAProxy using Certbot software. With our [Server Management Services,](https://bobcares.com/server-management/) Bobcares offers solutions to your Certbot and HAProxy queries.

Secure HAProxy using Certbot

In order to secure the HAProxy, we need to follow the below steps:

1. Let’s Encrypt Client Setup

2. Certificate Obtainment

3. HAProxy Setup

Let’s Encrypt Client Setup

1. The installation of the Certbot app on the server is the first step in using Let’s Encrypt to get an SSL certificate. Let’s add the repository to our package manager using the below code:

sudo add-apt-repository ppa:certbot/certbot

2. Click ENTER to continue after confirmation. Now update the package cache to pick up the new package list:

sudo apt-get update

3. Install the Certbot package:

sudo apt-get install certbot

Certificate Obtainment

We’ve got the Certbot now. So we can go ahead with the SSL-obtaining process. We’ll use a standalone plugin to obtain an SSL certificate. Getting SSL certificates is fairly easy using the Standalone plugin. The Let’s Encrypt CA connects to the server and verifies the server’s authenticity before issuing a certificate by temporarily operating a tiny web server (on port 80 by default) on the server. Therefore, for this strategy to work, port 80 must not be in use.

So before attempting to use this plugin, make sure to stop your default web server, if it is utilizing port 80 (i.e., HTTP).

1. We can use the standalone plugin using the command:

sudo certbot certonly --standalone --preferred-challenges http --http-01-port 80 -d example.com -d [www.example.com](http://www.example.com)

2. Provide the email address and agree to the Let’s Encrypt terms of service when asked. Now the HTTP challenge will run. Once it is successful, Certbot will print an output message showing the SSL certificate is saved.

3. Now, we’ll have the following PEM-encoded files: cert.pem, chain.pem, fullchain.pem, and privkey.pem.

4. It’s necessary to know the newly generated certificate file’s location. So we can use them when configuring the web server. The actual files are stored in the /etc/letsencrypt/archive folder. But in the /etc/letsencrypt/live/your_domain_name directory, Certbot establishes symbolic links to the most recent certificate files.

5. By using the command listed below, we may verify that the files are present. The four certificate files indicated above should be the output.

sudo ls /etc/letsencrypt/live/your_domain_name

6. We must merge fullchain.pem and privkey.pem into a single file when setting HAProxy to execute SSL termination so it will encrypt traffic between itself and the end user. So, make the directory where the combined file will be placed, /etc/haproxy/certs:

sudo mkdir -p /etc/haproxy/certs

7. Next, create the combined file with this cat command:

DOMAIN='example.com' sudo -E bash -c 'cat /etc/letsencrypt/live/$DOMAIN/fullchain.pem /etc/letsencrypt/live/$DOMAIN/privkey.pem > /etc/haproxy/certs/$DOMAIN.pem'

8. With the below command, we can protect access to the combined file, which has the private key:

sudo chmod -R go-rwx /etc/haproxy/certs

9. The SSL certificate and private key are now ready to use along HAProxy.

HAProxy Setup

1. Access the HAProxy configuration file using a text editor and keep it open:

sudo nano /etc/haproxy/haproxy.cfg

2. In the global section, include the following line:

maxconn 2048

3. Include the below line to set up the maximum size of temporary DHE keys that are generated:

tune.ssl.default-dh-param 2048

4. Include the below lines under the defaults section:

option forwardfor

option http-server-close

5. Now with the frontend sections, we want to add a frontend to handle incoming HTTP connections, and send them to a default backend. At the end of the file, let’s add a frontend called www-http. Be sure to replace haproxy_public_IP with the public IP address of our HAProxy server:

frontend www-http  
   bind haproxy_www_public_IP:80  
   reqadd X-Forwarded-Proto:\ http  
   default_backend www-backend

6. Next, we will add a frontend to handle incoming HTTPS connections. Add the frontend www-https at the end of the file.. Be sure to replace haproxy_www_public_IP with the public IP of our HAProxy server. Also, we will need to replace example.com with our domain name:

frontend www-https  
   bind haproxy_www_public_IP:443 ssl crt /etc/haproxy/certs/example.com.pem  
   reqadd X-Forwarded-Proto:\ https  
   acl letsencrypt-acl path_beg /.well-known/acme-challenge/  
   use_backend letsencrypt-backend if letsencrypt-acl  
   default_backend www-backend

This frontend uses an ACL (letsencrypt-acl) to send Let’s Encrypt validation requests (for /.well-known/acme-challenge) to the letsencrypt-backend backend, which will enable us to renew the certificate without stopping the HAProxy service. All other requests will be forwarded to the www-backend, which is the backend that will serve our web application or site.

7. After we finish configuring the frontends, add the www-backend backend by adding the following lines. Be sure to replace the highlighted words with the respective private IP addresses of our web servers. Any traffic that this backend receives will be balanced across its server entries, over HTTP (port 80):

backend www-backend  
   redirect scheme https if !{ ssl_fc }  
   server www-1 www_1_private_IP:80 check  
   server www-2 www_2_private_IP:80 check

8. Lastly, add the letsencrypt-backend backend, by adding these lines

backend letsencrypt-backend  
   server letsencrypt 127.0.0.1:54321

This backend, which only handles Let’s Encrypt ACME challenges that are used for certificate requests and renewals, sends traffic to the localhost on port 54321. We’ll use this port instead of 80 and 443 when we renew our Let’s Encrypt SSL certificate.

9. Now we’re ready to start HAProxy:

$ sudoservicehaproxy restart

[Looking for a solution to another query? [We are just a click away.](https://bobcares.com/server-management/)]

Conclusion

Typically, Certbot is used to convert an HTTP site to work in HTTPS. To conclude, the article explains the steps in detail to secure the HAProxy using the Certbot app.

From <[https://bobcares.com/blog/certbot-haproxy/](https://bobcares.com/blog/certbot-haproxy/)>