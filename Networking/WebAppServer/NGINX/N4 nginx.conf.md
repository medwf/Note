Main configuration:
``` NGINX
http {

	# you will have problem that NGINX can't read type file to help him do that define types

types {

Test/css    css; # that help NGINX to new that all file .css is css file

# there is a lot of types so nginx came with all types in /etc/nginx/mime.types

# to do that we will include that directive outside this type

}

Include mime.types; # here is all types we wanna handle.

# config nginx to be load balance:

upstream backendserver {

server IP_address:PORT;

# you can have multitype server here with deferent port

}

# in server you need to define location to server like this

location / {

proxy_pass [http://nameofbackendserver/](http://nameofbackendserver/); # I named it backendserver

}

# config nginx server:

# this server actually in /etc/nginx/sites-available/default

# we use it by typing:

include /etc/nginx/sites-enabled /* or /etc/nginx/sites-available/*;

server {

	listen 8080; # this server should listen to that port.
	root /path/to/folder; # folder of project you have html on it as root IP:port/
	# using LOCALION :     redirection with root
	location /path/you/want/to/define {
	root /path/to/folder; # the PATH will be /path/to/folder + /path/you/want/to/define
	# /path/to/folder/path/you/want/to/define

}

# using LOCATION:     redirection with alias.

location /path {

alias root /path/to/folder; # if you type /path they will serve /path/to/folder directive for you, without append /path.

# try_files : try does file if not exists then send 404 error

try_files /path/index.html /index.html =404;

}

# location with regular excretion

location ~* /path/[0-9] {  # if user type /path/[any number between 0 and 9] send him to root folder

root /root/folder; # root folder

try_files /index.html =404; # try index.html file if not exists send 404 error

}

# redirection : mean send you to another path or website

location /path/user/type {

return 307 /path/to send or website;

}

# rewrite : change path to something else

rewrite ^/path/(\w+) /PATH/$1;  # take that \w word to variable $1
}
}
```