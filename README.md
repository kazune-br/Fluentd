# Fluentd
This is a test repo to understand how Fluentd works.

## How to use this app
```
$ cd nginx
$ docker build -t nginx .
$ docker run --name nginx_server -d -p 8080:80 nginx:latest
$ http://localhost:8080
$ docker exec -it nginx_server /bin/bash
$ cat /var/log/nginx/access.log
```
