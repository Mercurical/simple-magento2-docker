FROM php:7.1-fpm-alpine

RUN cp /usr/local/etc/php/php.ini-development php.ini

RUN apk upgrade --update && \
    apk add libmemcached-dev libpng-dev libmcrypt-dev icu-dev libxslt-dev libjpeg-turbo-dev freetype-dev && \
    docker-php-ext-install pdo_mysql mcrypt intl xsl soap zip bcmath

RUN docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ --with-png-dir=/usr/include/ && \
    docker-php-ext-install -j$(getconf _NPROCESSORS_ONLN) gd

RUN apk add --no-cache $PHPIZE_DEPS && \
    pecl install xdebug-2.6.0

RUN docker-php-ext-enable xdebug

RUN mkdir -p /var/lib/php/session
RUN chmod 777 -R /var/lib/php/session