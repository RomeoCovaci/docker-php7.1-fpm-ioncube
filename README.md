## php-fpm 7.1 with ioncube loader and other php ext(gd, redis, mongodb etc)

__pull from docker hub:__
```
docker pull jeffhtli/php7.1-fpm-ioncube
```

__example with nginx:__
```
version: '2'
services:
  nginx:
    image: nginx
    volumes:
      - ./<YOUR_CONFIG_FILE>:/etc/nginx/conf.d/default.conf
      - ./:/usr/share/nginx/html
    ports:
      - "80:80"
  php-fpm:
    image: jeffhtli/php7.1-fpm-ioncube
    volumes:
      - ./:/usr/share/nginx/html
  redis:
    image: redis

```