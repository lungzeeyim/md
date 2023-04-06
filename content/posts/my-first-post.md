---
title: "This site is powered by Hugo"
date: 2023-03-11T20:11:34+08:00
draft: false
categories: [Setup]
tags: ['Hugo', 'commands', 'nginx', 'domain name']
---

## Hugo basic operations
------------------------
##### New post
```
hugo new posts/my-first-post.md
```

##### start server
```
hugo server -D
```

##### public
```
hugo
```

##### additonal setting for each post (categories and tags)
```
categories: [Setup]
tags: ['Hugo', 'commands', 'nginx', 'domain name']
```

## Local useful commands
-----------------------
##### SSH shotcut
create/modify file `~/.ssh/config`
```config
Host shotcutName
HostName 12.12.12.12
Port 3211
User root
```
after that, you can jsut run and get rid of long command:
```
ssh shotcutName
```

##### Upload everything in `public` folder to your server's folder
```
scp -r public/* shotcut:~/siteFiles
```

##### alias shotcut
```
# `hugos` for running the server at anywhere
alias hugos="cd ~/Documents/md/ && hugo server -D"

# `note` for opening the neovim at hugo foler
alias note="cd ~/Documents/md/ && nvim ."

# `generate` public files & upl for uploading public files to VPS
alias upl="cd ~/Documents/md/ && hugo && scp -r ~/Documents/md/public/* zeeyim:~/blog/"
```

## Domain Name DNS
--------------------
Just add exactly one www record:
```
A  www  example.com  192.1.2.3  3600
```

## NGINX Setup
----------------
##### Basic
- install NGINX...
```bash
$ apt update
$ apt install nginx
```
- restart nginx
```
systemctl restart nginx
``` 
- check configuration whether it is correct
```
/etc/nginx/sbin/nginx -t
```
##### Modiy configuration `/etc/nginx/conf/nginx.conf`
HTTP
```
server {
    listen       80;
    server_name  zeeyim.com www.zeeyim.com;
    location / {

        # change the PATH to your path
        root   /PATH;

        index  index.html index.htm;
    }
```
HTTPS
- certificate file (from https://www.sslforfree.com/):
    - certificate.crt
    - private.key
```
server {
    listen  443 ssl;
    server_name zeeyim.com  www.zeeyim.com;

    # change the PATH to your path
    root    /PATH; 

    index   index.html  index.htm;

    # change the PATH to your path
    ssl_certificate /PATH/certificate.crt;
    ssl_certificate_key /PATH/cert/private.key;

    location / {
        index index.html index.htm;
    }
}
```

reference:
https://kbudaj.com/2018/11/how-to-setup-hugo-on-vps/#create-droplet



