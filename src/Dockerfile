FROM alpine:3.1
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    APACHE2_UTILS_VERSION=2.4.16-r0 \
    NGINX_VERSION=1.6.2-r1

RUN set -x \
    && apk add -U \
        apache2-utils=$APACHE2_UTILS_VERSION \
        nginx=$NGINX_VERSION \
    && ln -sf /dev/stdout /var/log/nginx/access.log \
    && ln -sf /dev/stderr /var/log/nginx/error.log \
    && rm -rf /var/cache/apk/*

COPY ./root /

ENTRYPOINT [ "/usr/sbin/nginx" , "-g" , "daemon off;" ]
