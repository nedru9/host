FROM php:8.4-fpm


RUN rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY ./_docker/app/php.ini /usr/local/etc/php/conf.d/php.ini

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php --  \
    --filename=composer  \
    --install-dir=/usr/local/bin

WORKDIR /var/www
