FROM php:8.0-fpm

RUN apt-get update && apt-get install -y nodejs npm zlib1g-dev g++ git curl libpng-dev libicu-dev libonig-dev libxml2-dev zip libzip-dev zip unzip unixodbc-dev \
    && docker-php-ext-install intl opcache pdo pdo_mysql mbstring exif pcntl bcmath gd \
    && pecl install apcu sqlsrv pdo_sqlsrv \
    && docker-php-ext-enable apcu sqlsrv pdo_sqlsrv \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

WORKDIR /var/www/project

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer create-project laravel/laravel app