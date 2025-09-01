FROM php:fpm

ARG DOCKERFILE_DIRECTORY
ARG UID

RUN docker-php-ext-install opcache
COPY php/${DOCKERFILE_DIRECTORY}/opcache.ini /usr/${DOCKERFILE_DIRECTORY}/etc/php/conf.d/opcache.ini
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get update && apt-get install -y git wget zip unzip libjpeg62-turbo-dev libpng-dev libfreetype6-dev libxslt-dev \
    libzip-dev libldap2-dev bash libaio-dev ca-certificates nodejs npm libicu-dev

RUN docker-php-ext-install intl ldap zip mysqli pdo pdo_mysql gd ftp

RUN mkdir -p /var/www/html
COPY . /var/www/html
RUN chown -R ${UID}:www-data storage/* && \
    composer install && \
    npm install
