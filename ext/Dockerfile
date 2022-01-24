ARG PHP_VERSION
ARG PHP_EXTENSION
ARG REPO_OWNER=opentelemetry-php
ARG REPO=php-base-img

FROM ghcr.io/${REPO_OWNER}/php/cli:${PHP_VERSION}

LABEL org.opencontainers.image.source=https://github.com/opentelemetry-php/php-base-img

RUN install-php-extensions ${PHP_EXTENSION} ; \
    # strip debug symbols from extensions to reduce size
    find /usr/local/lib/php/extensions -name "*.so" -exec strip --strip-debug {} \;; \
    find /usr/local/lib/php/extensions -type d -exec chmod +x -R {} \;;
