FROM  php:7.4-fpm-buster

RUN apt-get update \
    && apt-get install -y git acl openssl openssh-client wget zip nano librabbitmq-dev libssh-dev libpq-dev libxslt-dev \
    && apt-get install -y libpng-dev zlib1g-dev libzip-dev libxml2-dev libicu-dev libsodium23\
    && docker-php-ext-install intl pdo pdo_mysql pdo_pgsql zip gd soap bcmath sockets xsl \
    && pecl install xdebug amqp mongodb \
    && docker-php-ext-enable --ini-name 05-opcache.ini opcache amqp xdebug mongodb

RUN curl -sS https://getcomposer.org/installer | php && \
    mv composer.phar /usr/local/bin/composer && \
    chmod +x /usr/local/bin/composer

WORKDIR /usr/share/nginx/html

EXPOSE 9003