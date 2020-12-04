FROM php:7.4-fpm-alpine

ARG GID
ARG GROUP
ARG UID
ARG USER
ARG WORKDIR

# Use the default PHP development configuration.
RUN set -eux; \
    cp "$PHP_INI_DIR/php.ini-development" "$PHP_INI_DIR/php.ini"

RUN set -eux; \
    addgroup -g ${GID} ${GROUP}; \
    adduser -D -g ${GID} -G ${GROUP} -s /bin/sh -u ${UID} ${USER}; \
    mkdir -p ${WORKDIR}; \
    chown ${UID}:${GID} ${WORKDIR}

## Install extensions.
COPY --from=mlocati/php-extension-installer \
    /usr/bin/install-php-extensions /usr/bin

RUN set -eux; \
    install-php-extensions \
        bcmath \
        pdo_mysql

### Install additional packages.
RUN set -eux; \
    apk --no-cache add \
        autoconf \
        g++ \
        make

RUN set -eux; \
    pecl install xdebug-2.9.8; \
    docker-php-ext-enable xdebug

COPY ./usr/local/etc/php/conf.d/zz-custom-settings.ini \
    /usr/local/etc/php/conf.d/zz-custom-settings.ini
