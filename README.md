# サーバ起動

reverse proxy

```
$ nginx -p . -c ./nginx.conf
```

app server

```shell
$ rackup
```

# curlで叩く

```shell
$ curl -I http://localhost:80/
```

# 結果

rev proxy

```shell
127.0.0.1 - - [22/May/2023:14:53:03 +0900] "HEAD / HTTP/1.1" 200 0 "-" "curl/7.85.0" "-" "3.009" "3.009"
```

app server

```shell
127.0.0.1 - - [25/Jun/2012 23:24:33] "HEAD / HTTP/1.1" 200 - 3.0018
```

curl
```shell
$ curl -I http://localhost:9291/
HTTP/1.1 200 OK
Server: nginx/1.23.4
Date: Mon, 22 May 2023 03:00:05 GMT
Content-Type: text/plain
Content-Length: 0
Connection: keep-alive
X-Runtime: 3.002419
```
