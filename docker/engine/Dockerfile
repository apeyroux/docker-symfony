FROM php:5.6-fpm

RUN apt-get update \
    && apt-get install -y \
        libicu-dev \
        zlib1g-dev \
    && docker-php-ext-install -j$(nproc) \
        intl \
        mbstring \
        pdo_mysql \
        zip \
    && php -r "readfile('https://getcomposer.org/installer');" | php -- --install-dir=/usr/local/bin --filename=composer \
    && chmod +x /usr/local/bin/composer

RUN usermod -u 1000 www-data
