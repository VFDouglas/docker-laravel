FROM php:fpm-alpine
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apk add git jpeg-dev libpng-dev freetype-dev libxslt-dev icu-dev libzip-dev bash openldap-dev
RUN docker-php-ext-install intl
RUN docker-php-ext-install ldap
RUN docker-php-ext-install zip
RUN mkdir -p /var/www/html
COPY . /var/www/html
WORKDIR /var/www/html
RUN composer install
