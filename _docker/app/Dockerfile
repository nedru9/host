FROM php:8.4-fpm


RUN apt-get update && apt-get install -y \
     libpq-dev \
     libpng-dev \
     libzip-dev \
     zip unzip \
     git \
     docker-php-ext-install pdo_mysql bcmath gd zip && \
     apt-get clean && \
     rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY ./_docker/app/php.ini /usr/local/etc/php/conf.d/php.ini

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN apt-get update && apt-get install -y wget  \
    && wget -O - https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer  \
    && apt-get clean  \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /var/www
