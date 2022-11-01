FROM mediawiki:stable

RUN apt-get update && \
    apt-get install -y --no-install-recommends unzip && \
    apt-get purge -y --auto-remove

RUN mv /var/www/html /var/www/html.old && \
    mkdir /var/www/html && \
    mv /var/www/html.old /var/www/html/mediawiki

COPY composer.local.json /var/www/html/mediawiki/

RUN cd /var/www/html/mediawiki/extensions && \
    git clone --single-branch --branch=REL1_38 --depth=1 https://github.com/wikimedia/mediawiki-extensions-PluggableAuth.git PluggableAuth && \
    git clone --single-branch --branch=REL1_38 --depth=1 https://github.com/wikimedia/mediawiki-extensions-OpenIDConnect.git OpenIDConnect

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN cd /var/www/html/mediawiki && \
    composer update