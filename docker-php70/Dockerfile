FROM php:7.0-apache

# Add apache2 mod rewrite
RUN a2enmod rewrite

RUN apt update

# Install git and zip/unzip for sources and composer install scripts
RUN apt install git zip unzip -y

# Install xdebug and the appropriate php zip package via pecl
RUN pecl install xdebug-2.5.0 zip \
    && docker-php-ext-enable xdebug

WORKDIR /usr/local/bin/
# Copy default php ini
COPY php.ini /usr/local/etc/php/conf.d/php.ini
# copy composer script and run it
COPY install-composer.sh /usr/local/bin/build.sh
RUN /bin/bash -c "source /usr/local/bin/build.sh"
WORKDIR /var/www/html/
