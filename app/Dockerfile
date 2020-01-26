FROM composer:latest as build

COPY src/composer.* /app/
RUN composer install --no-dev --no-autoloader --ansi
COPY src /app
RUN composer dump-autoload --no-dev -o --ansi

FROM ntsuchiya1105/laravel-base:0.2 as base

COPY --from=build --chown=nginx:nginx /app /app
