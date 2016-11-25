# SSL Monkey

_for internal use_

Automated SSL Proxy with [jwilder/nginx-proxy](https://github.com/jwilder/nginx-proxy) and [JrCs/docker-letsencrypt-nginx-proxy-companion](https://github.com/JrCs/docker-letsencrypt-nginx-proxy-companion).

Simply connect to the `www` network on other containers or in a `docker-compose.yml` as follows:

```
version: '2'
networks:
  www:
    external: true
services:
  app:
    image: mywebserverimage
    environment:
      VIRTUAL_HOST: example.com
      LETSENCRYPT_HOST: example.com
      LETSENCRYPT_EMAIL: user@example.com
    networks:
      - www
```
