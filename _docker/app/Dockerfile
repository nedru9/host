FROM php:8.4-fpm


RUN apt-get update && apt-get install -y \
     apt-utils \
     libpq-dev \
     libpng-dev \
     libzip-dev \
     zip unzip \
     git \
     curl && \
     docker-php-ext-install pdo_mysql bcmath gd zip && \
     apt-get clean && \
     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY ./_docker/app/php.ini /usr/local/etc/php/conf.d/php.ini

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php --  \
    --filename=composer  \
    --install-dir=/usr/local/bin

WORKDIR /var/www
