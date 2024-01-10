FROM nginx:alpine
COPY ./nginx/default.conf /etc/nginx/conf.d
RUN mkdir -p /var/www/html
COPY . /var/www/html/
