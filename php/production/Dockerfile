FROM php:fpm-alpine
RUN docker-php-ext-install opcache
COPY php/production/opcache.ini /usr/local/etc/php/conf.d/opcache.ini
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN docker-php-ext-install intl ldap zip
RUN mkdir -p /var/www/html
COPY . /var/www/html
