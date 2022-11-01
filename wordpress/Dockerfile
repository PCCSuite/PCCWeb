FROM wordpress:php8.1-fpm-alpine

COPY entrypoint.sh /

WORKDIR /var/www/html/wordpress
ENTRYPOINT ["/entrypoint.sh"]