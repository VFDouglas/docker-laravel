<<<<<<< HEAD
FROM php:fpm
RUN docker-php-ext-install opcache
COPY php/local/opcache.ini /usr/local/etc/php/conf.d/opcache.ini
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get update && apt-get install -y git libjpeg62-turbo-dev libpng-dev libfreetype6-dev libxslt-dev libzip-dev libldap2-dev bash
RUN apt-get install -y nodejs npm
RUN docker-php-ext-install intl ldap zip mysqli pdo pdo_mysql gd ftp
RUN mkdir -p /var/www/html
COPY . /var/www/html
=======
FROM php:fpm-alpine
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apk --no-cache add git jpeg-dev libpng-dev freetype-dev libxslt-dev icu-dev libzip-dev bash openldap-dev
RUN apk --no-cache add --update nodejs npm
RUN docker-php-ext-install intl ldap zip mysqli pdo pdo_mysql gd
RUN mkdir -p /var/www/html
COPY . /var/www/html
>>>>>>> 56869c8f6d5ab984be68f4532504e6d91eae5b7d