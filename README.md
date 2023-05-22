# サーバ起動

nginx

```
$ nginx -p . -c ./nginx.conf -g "daemon off;"
```


upstream server

```shell
$ rackup
```

# curlで叩く

```shell
$ curl -I http://localhost:80/
```

# 結果

nginx（`./logs/access.log` に吐かれる）

```shell
127.0.0.1 - - [22/May/2023:14:53:03 +0900] "HEAD / HTTP/1.1" 200 0 "-" "curl/7.85.0" "-" "3.009" "3.009"
```

upstream server

```shell
127.0.0.1 - - [25/Jun/2012 23:24:33] "HEAD / HTTP/1.1" 200 - 3.0018
```

curl
```shell
$ curl -I http://localhost:80/
HTTP/1.1 200 OK
Server: nginx/1.23.4
Date: Mon, 22 May 2023 03:00:05 GMT
Content-Type: text/plain
Content-Length: 0
Connection: keep-alive
X-Runtime: 3.002419
```

# FYI

nginx

```
$ nginx -help
nginx version: nginx/1.23.4
Usage: nginx [-?hvVtTq] [-s signal] [-p prefix]
             [-e filename] [-c filename] [-g directives]

Options:
  -?,-h         : this help
  -v            : show version and exit
  -V            : show version and configure options then exit
  -t            : test configuration and exit
  -T            : test configuration, dump it and exit
  -q            : suppress non-error messages during configuration testing
  -s signal     : send signal to a master process: stop, quit, reopen, reload
  -p prefix     : set prefix path (default: /usr/local/Cellar/nginx/1.23.4/)
  -e filename   : set error log file (default: /usr/local/var/log/nginx/error.log)
  -c filename   : set configuration file (default: /usr/local/etc/nginx/nginx.conf)
  -g directives : set global directives out of configuration file
```