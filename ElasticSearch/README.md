## How to use this app
```
# ref: https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html
# Imageのダウンロード
$ docker pull docker.elastic.co/elasticsearch/elasticsearch:6.4.2
# ES起動
$ docker run -p 9200:9200 -p 9300:9300 -d -e "discovery.type=single-node" docker.elastic.co/elasticsearch/elasticsearch:6.4.2
# 起動確認
$ curl -XGET http://localhost:9200/
# Nodeの中に入る
$ docker exec -it id /bin/bash
# ESの設定確認
$ cat /elasticsearch/config/elasticsearch.yml
```
