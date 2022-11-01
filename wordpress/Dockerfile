FROM wordpress:php8.1-fpm-alpine

COPY entrypoint.sh /

RUN mkdir /var/www/html/wordpress

WORKDIR /var/www/html/wordpress
ENTRYPOINT ["/entrypoint.sh"]