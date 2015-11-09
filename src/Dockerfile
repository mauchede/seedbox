FROM debian:jessie
MAINTAINER Morgan Auchede <morgan.auchede@gmail.com>

ENV \
    DEBIAN_FRONTEND=noninteractive \
    APACHE2_UTILS_VERSION=2.4.10 \
    LIBPAM_PWDFILE_VERSION=1.0

RUN set -x \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        apache2-utils=$APACHE2_UTILS_VERSION* \
        libpam-pwdfile=$LIBPAM_PWDFILE_VERSION* \
    && mkdir -p /etc/seedbox \
    && touch /etc/seedbox/users \
    && cp /lib/x86_64-linux-gnu/security/pam_permit.so /usr/local/lib \
    && cp /lib/x86_64-linux-gnu/security/pam_pwdfile.so /usr/local/lib \
    && rm -rf /etc/pam.d/* /var/lib/apt/lists/*

COPY ./etc /etc
COPY ./usr /usr
