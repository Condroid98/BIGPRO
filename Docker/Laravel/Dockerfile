FROM php:7.4-apache

RUN apt-get update && apt-get install -y openssl zip unzip git \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli 

WORKDIR /app

COPY --from=composer:2.1.8 /usr/bin/composer /usr/local/bin/composer

COPY . /app

RUN composer install

CMD php artisan serve --host=0.0.0.0 --port=80

EXPOSE 80
