FROM php:7.0-apache

# Install Xdebug
RUN apt-get update && apt-get install -y vim \
    && pecl install xdebug-2.5.5 && docker-php-ext-enable xdebug

# Configure PHP
RUN echo "\
    short_open_tag = On" > /usr/local/etc/php/php.ini

# Configure xDebug
RUN echo "\n\
    xdebug.default_enable=1\n\
    xdebug.remote_enable=1\n\
    xdebug.remote_connect_back=1\n\
    xdebug.remote_port=9000\n\
    xdebug.idekey=VSCODE \n\
    xdebug.remote_log=/var/www/html/xdebug.log\n\
    ">> /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

WORKDIR /var/www/html

