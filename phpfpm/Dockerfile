FROM php:fpm
COPY sources.list /etc/apt/sources.list
RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    libbz2-dev \
    libxml2-dev \
    && docker-php-ext-install -j$(nproc) iconv mysqli mcrypt bz2 pdo pdo_mysql zip json xml xmlrpc \
    && docker-php-ext-configure gd \
    && docker-php-ext-install -j$(nproc) gd \
    && pecl install redis \
    && docker-php-ext-enable redis opcache

