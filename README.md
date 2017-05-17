# Shadowsocks/Privoxy Docker container
Fork of [fangqiuming/docker-sslocal](https://github.com/fangqiuming/docker-sslocal) but with the addition of privoxy http proxy.

## Building and running
```
docker build -t shadowsocks .
docker run -d -p 8118:8118 shadowsocks \
	-b 0.0.0.0 \
	-s $SS_SERVER_ADDRESS \
	-p $SS_SERVER_PORT \
	-l $SOCKS5_PORT \
	-k $SS_PASSWORD \
	-m ENCRYPTION_METHOD
```

## Start a container with access to proxy 
```
docker run -it --link shadowsocks \
	-e http_proxy=shadowsocks:8118 \
	-e https_proxy=shadowsocks:8118 \
	ubuntu:14.04 bash
```
  
