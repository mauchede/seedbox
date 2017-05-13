FROM ubuntu:latest

LABEL \
    maintainer="Morgan Auchede <morgan.auchede@gmail.com>"

ENV \
    S6_BEHAVIOUR_IF_STAGE2_FAILS=2 \
    S6_KEEP_ENV=1

RUN set -eux \

    # Prepare system

    && export BUILD_DEPS="ca-certificates curl unzip" \
    && export DEBIAN_FRONTEND=noninteractive \

    && apt-get update \

    # Install packages

    && apt-get install --no-install-recommends --yes \
           ${BUILD_DEPS} \
           nginx-full \
           openssh-server \

    # Install bootstrap

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/bootstrap/latest" | xargs) \

    && curl --location --output /tmp/bootstrap.zip "https://github.com/twbs/bootstrap/releases/download/v${BOOTSTRAP_VERSION}/bootstrap-${BOOTSTRAP_VERSION}-dist.zip" \
    && unzip /tmp/bootstrap.zip -d /tmp \
    && mkdir --parents /var/www/css \
    && mv "/tmp/bootstrap-${BOOTSTRAP_VERSION}-dist/css/bootstrap.min.css" /var/www/css/bootstrap.min.css \

    # Install s6-overlay

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/s6-overlay/latest" | xargs) \

    && curl --location "https://github.com/just-containers/s6-overlay/releases/download/v${S6_OVERLAY_VERSION}/s6-overlay-amd64.tar.gz" | tar --directory / --extract --gzip \

    # Install syslog-stdout

    && export $(curl "https://raw.githubusercontent.com/timonier/version-lister/release/generated/syslog-stdout/latest" | xargs) \

    && curl --location "https://github.com/timonier/syslog-stdout/releases/download/v${SYSLOG_STDOUT_VERSION}/syslog-stdout.tar.gz" | tar --directory /usr/sbin --extract --gzip \

    # Configure user "www-data"

    && usermod --append --groups shadow www-data \

    # Clean

    && apt-get remove --purge --yes \
           ${BUILD_DEPS} \

    && apt-get autoremove --purge --yes \

    && rm --force --recursive \
           /etc/ssh/ssh_host_* \
           /tmp/* \
           /var/lib/apt/lists/* \
           /var/log/*

COPY ./rootfs /

ENTRYPOINT [ "/init" ]
