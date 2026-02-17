FROM dunglas/frankenphp:1.11.2-builder-php8

RUN apt-get update && apt-get install -y vim git \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2.9 /usr/bin/composer /usr/bin/composer
COPY --from=oven/bun:1.3.9 /usr/local/bin/bun    /usr/bin/bun

COPY ./config/franken/Caddyfile /etc/frankenphp/Caddyfile

WORKDIR /var/www/html
