frontend FE # FE is the name of that frontend

Bind *:80 # * is Ip address 80 is port

bind *:443 ssl crt PATH/TO/THA/certificate/Privet/public/key alpn h2 , http/1.1

alpn : application layer protocol negotiation, It is extension of TLS

mode http # default mode is tcp now we will use http

Timeout client 60s # client shouldn't take more then 60s

# Using one backend server:

Default_backend BE # frontend should always listen to backend

# Using multi backend server: (using ACL access control list)

# name app? If path end with /app?

acl app1 path_end -i /app1

acl app2 path_end -i /app2

# use that backend if resaved that acl.

Use_backend app1server if app1

Use_backend app2server if app2

# Blog PATH

# I wanna blog all /admin

http-request deny if { path -I -m beg /admin }

# Using one backend

Backend BE # BE is the name of backend

time connect 10s # time connect immediately to server

time server 100s # time middle of request

mode http # make mode is http

# there is a lot of balance  :

source  : give every Ip address one server.

balance roundrobin  # it used roundrobin by default (123, 123)

server name server iPAddress:PORT   # define that server

.

.

.

# you can add a lot of server here ….

# Using two backend

Backend app1server # BE is the name of backend

time connect 10s # time connect immediately to server

time server 100s # time middle of request

mode http # make mode is http

server name server iPAddress:PORT   # define that server

.

.

.

# you can add a lot of server here ….

Backend app2server # BE is the name of backend

time connect 10s # time connect immediately to server

time server 100s # time middle of request

mode http # make mode is http

server name server iPAddress:PORT   # define that server

.

.

.

# you can add a lot of server here ….