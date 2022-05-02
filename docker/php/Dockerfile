FROM php:7.4-fpm-alpine

RUN apk add --update \
    make \
    curl

RUN docker-php-ext-install \ 
    mysqli \
    pdo_mysql \
    opcache

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer && \
    ln -s $(composer config --global home) /root/composer
ENV PATH=$PATH:/root/composer/vendor/bin COMPOSER_ALLOW_SUPERUSER=1

ADD php.ini /etc/php/conf.d/
ADD php.ini /usr/local/etc/php
ADD php-fpm.conf /etc/php/php-fpm.d/
ADD php-fpm.conf /usr/local/etc/php/php-fpm.d/

WORKDIR /var/www/app

EXPOSE 9000

CMD ["php-fpm", "-F"]