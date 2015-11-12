FROM alpine:3.1
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    APACHE2_UTILS_VERSION=2.4.16-r0

RUN set -x \
    && apk add -U apache2-utils=$APACHE2_UTILS_VERSION \
    && mkdir -p /etc/seedbox \
    && rm -rf /var/cache/apk/*

COPY bin /usr/bin
COPY nginx /etc/nginx/conf.d
COPY pam /etc/pam.d

ENTRYPOINT [ "/bin/sh" ]
