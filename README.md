# About this repo

[![Docker Stars](https://img.shields.io/docker/stars/gurukami/nginx.svg?style=flat)](https://hub.docker.com/r/gurukami/nginx/) [![Docker Pulls](https://img.shields.io/docker/pulls/gurukami/nginx.svg?style=flat)](https://hub.docker.com/r/gurukami/nginx/)

This is a Dockerfile instructions to build a container image with **Nginx** based on **nginx:1** docker image

## Configuration

Hostname: **sandbox.local** (80 - HTTP, 443 - SSL)  
Upstream PHP-FPM: **php:9000** (install apart, see https://github.com/Gurukami/docker-hub-php)  

**Don't forget update "hosts" file to resolve sandbox.local**

Windows: Windows\System32\drivers\etc\hosts  
Linux: /etc/hosts  

...  
127.0.0.1 sandbox.local  
127.0.0.1 php  
...  

## Usage

**Dockerfile**

FROM gurukami/nginx:latest
...

**Run container**

{host-src} - your folder of data on host machine for mount it into guest (virtual) machine

```
docker run --name gurukami_nginx -d -p 80:80 -p 443:443 -v {host-src}:/share gurukami/nginx:latest
```
  
Then you can hit http://sandbox.local (HTTP) or https://sandbox.local (HTTPS, SSL) in your browser.
For more information about run command, see https://docs.docker.com/engine/reference/run/

## License

The MIT license  
Copyright (c) 2016 Gurukami, http://gurukami.com/
