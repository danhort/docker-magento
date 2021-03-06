FROM php:7.1-fpm-jessie as magento_php

RUN apt-get update \
    && systemRequirements="wget nano nodejs-legacy" \
    && apt-get install -y $systemRequirements \
    && magentoRequirements="cron libpng12-dev libmcrypt-dev libmcrypt4 libcurl3-dev libfreetype6 libjpeg-dev libjpeg62-turbo libjpeg62-turbo-dev libpng12-dev libfreetype6-dev libicu-dev libxslt1-dev npm" \
    && apt-get install -y $magentoRequirements \
    && rm -rf /var/lib/apt/lists/* \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install gd \
    && docker-php-ext-install mcrypt \
    && docker-php-ext-install mbstring \
    && docker-php-ext-install zip \
    && docker-php-ext-install bcmath \
    && docker-php-ext-install intl \
    && docker-php-ext-install xsl \
    && docker-php-ext-install soap \
    && requirementsToRemove="libpng12-dev libmcrypt-dev libcurl3-dev libpng12-dev libfreetype6-dev libjpeg62-turbo-dev libjpeg-dev" \
    && apt-get purge --auto-remove -y $requirementsToRemove

## Install Composer globally
RUN rm -f /usr/local/bin/composer
ENV COMPOSER_ALLOW_SUPERUSER 1
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer self-update --1
RUN composer config --global repos.packagist composer https://packagist.org 
RUN composer global require "hirak/prestissimo" "mage2tv/magento-cache-clean" --no-plugins --no-suggest --optimize-autoloader --classmap-authoritative
ENV PATH "${PATH}:/root/.composer/vendor/bin"

# Install Magerun 2
# Magerun >= v2.4 does not support PHP <= 7.1
RUN wget https://files.magerun.net/n98-magerun2-3.2.0.phar \
	&& chmod +x ./n98-magerun2-3.2.0.phar \
    && mv ./n98-magerun2-3.2.0.phar /usr/local/bin/n98

RUN chmod 777 -Rf /var/www /var/www/.* \
	&& chown -Rf www-data:www-data /var/www /var/www/.* \
    && usermod -u 1000 www-data

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

FROM magento_php as magento_php_xdebug

# Install xdebug
RUN pecl install xdebug \
    && docker-php-ext-enable xdebug
