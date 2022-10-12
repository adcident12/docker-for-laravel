FROM php:8.0-fpm

RUN apt-get update && apt-get install -y gnupg unixodbc unixodbc-dev vim nano nodejs npm zlib1g-dev g++ git curl libpng-dev libicu-dev libonig-dev libxml2-dev zip libzip-dev zip unzip \
    && docker-php-ext-install intl opcache pdo pdo_mysql mbstring exif pcntl bcmath gd \
    && pecl install apcu \
    && docker-php-ext-enable apcu \
    && docker-php-ext-configure zip \
    && docker-php-ext-install zip

RUN apt-get update \
    && curl https://packages.microsoft.com/keys/microsoft.asc | apt-key add - \
    && curl https://packages.microsoft.com/config/debian/9/prod.list > /etc/apt/sources.list.d/mssql-release.list \
    && apt-get update \
    && ACCEPT_EULA=Y apt-get install --yes --no-install-recommends msodbcsql18 mssql-tools18 \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/* \
    && rm -rf /tmp/*

RUN pecl install pdo_sqlsrv sqlsrv \
    && docker-php-ext-enable pdo_sqlsrv sqlsrv


WORKDIR /var/www/project

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer