# Nginx Server

## How to use nginx
```
# コンテナ起動0
$ cd nginx
$ docker build -t nginx .
$ docker run --name nginx_server -d -p 8080:80 nginx:latest

# 外側から動作確認
$ curl http://localhost:8080

# 内側から動作確認
$ docker exec -it nginx_server /bin/bash
$ cat /var/log/nginx/access.log
```
