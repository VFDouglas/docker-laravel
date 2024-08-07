FROM php:fpm
RUN docker-php-ext-install opcache
COPY php/production/opcache.ini /usr/local/etc/php/conf.d/opcache.ini
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apt-get update && apt-get install -y git libjpeg62-turbo-dev libpng-dev libfreetype6-dev libxslt-dev libzip-dev libldap2-dev bash
RUN apt-get install -y nodejs npm
RUN docker-php-ext-install intl ldap zip mysqli pdo pdo_mysql gd ftp
RUN mkdir -p /var/www/html
COPY . /var/www/html

RUN chown www-data:www-data -R /var/www/html
