ARG PHP_VERSION=7.4
ARG PHP_SAPI=cli
ARG PHP_OS=alpine
ARG REPO_OWNER=opentelemetry-php
ARG REPO=php-base-img

FROM php:${PHP_VERSION}-${PHP_SAPI}-${PHP_OS}

LABEL org.opencontainers.image.source=https://github.com/opentelemetry-php/php-base-img

ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

RUN   chmod +x /usr/local/bin/install-php-extensions; \
      install-php-extensions \
        sockets \
        @composer \
      ; \
      apk add --no-cache binutils bash git; \
      addgroup -g "1000" -S php; \
      adduser --system \
        --gecos "" \
        --ingroup "php" \
        --uid "1000" \
        "php";

