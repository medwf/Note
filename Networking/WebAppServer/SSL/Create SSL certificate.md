1. Installation :

- sudo apt-get update -y
-  sudo apt-get install certbot
- certbot --version
- `sudo certbot certonly --standalone -d www.okinnovator.tech`

- Add your email address
- Agree
- Show email address

1. Where your certificate ?

- "take trust for them to start encryption https request"

- Public key will found it in path:

- /etc/letsencrypt/live/domain-name/fullchain.pem

- Privet key will found it in path:

- /etc/letsencrypt/live/domain-name/privkey.pem

1. Config HAProxy to use ssl certificate :

- HAProxy wanna one file contain public and privet key.
- sudo mkdir -p /etc/haproxy/certs
- DOMAIN='www.okinnovator.tech' sudo -E bash -c 'cat /etc/letsencrypt/live/$DOMAIN/fullchain.pem /etc/letsencrypt/live/$DOMAIN/privkey.pem > /etc/haproxy/certs/$DOMAIN.pem'
-  sudo chmod -R go-rwx /etc/haproxy/certs # delete rwx from group and owner.

- DOMAIN='www.workhubconnect.me' sudo -E bash -c 'cat /etc/letsencrypt/live/$DOMAIN/fullchain.pem /etc/letsencrypt/live/$DOMAIN/privkey.pem > /etc/haproxy/certs/$DOMAIN.pem'

 # with nginx 
 - `sudo certbot --nginx -d example.com -d www.example.com` 