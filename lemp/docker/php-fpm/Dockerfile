FROM php:7.0.8-fpm-alpine

RUN apk update && apk upgrade && \
    apk add --update curl wget bash tree autoconf gcc g++ make libffi-dev openssl-dev

RUN pecl install xdebug \
	&& docker-php-ext-enable xdebug \
	&& docker-php-ext-install opcache

RUN docker-php-ext-install pdo_mysql

COPY ./conf/php-dev.ini /usr/local/etc/php/
COPY ./conf/php-prod.ini /usr/local/etc/php/
COPY ./conf/envars-development.conf /usr/local/etc/php-fpm.d
COPY . /usr/share/nginx/html
WORKDIR /usr/share/nginx/html

CMD [ "php-fpm", "-c", "/usr/local/etc/php/php-dev.ini" ]