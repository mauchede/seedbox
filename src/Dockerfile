FROM alpine:3.3
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    BOOTSTRAP_VERSION=3.3.6 \
    S6_OVERLAY_VERSION=1.17.1.2 \
    SYSLOG_STDOUT_VERSION=1.1.1

RUN set -x \

    # Prepare system

    && apk add -U \

    # Install packages

    && BUILD_DEPS="curl unzip" \

    && apk add \
           $BUILD_DEPS \
           apache2-utils \
           nginx \


    # Install bootstrap

    && curl -ksLo /tmp/bootstrap.zip "https://github.com/twbs/bootstrap/releases/download/v$BOOTSTRAP_VERSION/bootstrap-$BOOTSTRAP_VERSION-dist.zip" \
    && unzip /tmp/bootstrap.zip -d /tmp \
    && mkdir -p /var/www/css \
    && mv /tmp/bootstrap-$BOOTSTRAP_VERSION-dist/css/bootstrap.min.css /var/www/css/bootstrap.min.css \


    # Install s6-overlay

    && curl -ksL "https://github.com/just-containers/s6-overlay/releases/download/v$S6_OVERLAY_VERSION/s6-overlay-amd64.tar.gz" | tar fxz - -C / \

    # Install syslog-stdout

    && curl -ksL "https://github.com/timonier/syslog-stdout/releases/download/v$SYSLOG_STDOUT_VERSION/syslog-stdout.tar.gz" | tar fxz - -C /usr/sbin \

    # Clean

    && apk del \
           $BUILD_DEPS \

    && rm -rf \
           /tmp/* \
           /var/cache/apk/*

COPY ./rootfs /

ENTRYPOINT [ "/init" ]
