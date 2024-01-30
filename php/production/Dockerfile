FROM php:fpm-alpine
RUN docker-php-ext-install opcache
COPY php/opcache.ini /usr/local/etc/php/conf.d/opcache.ini
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN apk --no-cache add git jpeg-dev libpng-dev freetype-dev libxslt-dev icu-dev libzip-dev bash openldap-dev
RUN apk --no-cache add --update nodejs npm
RUN docker-php-ext-install intl ldap zip mysqli pdo pdo_mysql gd
RUN mkdir -p /var/www/html
COPY . /var/www/html