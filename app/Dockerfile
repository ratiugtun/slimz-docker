FROM php:7.2-apache

ARG BRANCH
ENV BRANCH ${BRANCH:-master}

RUN apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git libyaz4-dev yaz libpng-dev libjpeg-dev libwebp-dev

RUN pecl install yaz

RUN docker-php-ext-configure gd

RUN docker-php-ext-install -j$(nproc) pdo pdo_mysql mysqli gd gettext mbstring

RUN git clone --depth 1 -b $BRANCH \
    https://github.com/slims/slims9_bulian.git \
    /var/www/html/

COPY php.ini $PHP_INI_DIR/conf.d/custom.ini

# Assige appropriate permission
RUN find -type d -print0 | xargs -0 chown -R www-data:www-data && \
    find -type f -print0 | xargs -0 chown -R www-data:www-data && \
    find -type d -print0 | xargs -0 chmod -R 755 && \
    find -type f -print0 | xargs -0 chmod -R 644

VOLUME [ "./app/slims" ]

WORKDIR /var/www/html