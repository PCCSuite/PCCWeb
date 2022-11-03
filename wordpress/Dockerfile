FROM wordpress:php8.1-apache

COPY entrypoint.sh /

RUN mkdir /var/www/html/wordpress

WORKDIR /var/www/html/wordpress
ENTRYPOINT ["/entrypoint.sh"]
CMD ["apache2-foreground"]