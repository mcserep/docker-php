FROM php:7.4-apache

# Update package repository
RUN apt-get update -y
# Intall tools
RUN apt-get install -y git zip
# Install libraries
RUN apt-get install -y \
    libmcrypt-dev \
    libpq-dev \
    libcurl4-gnutls-dev \
    libicu-dev \
    libvpx-dev \
    libjpeg-dev \
    libpng-dev \
    libxpm-dev \
    zlib1g-dev \
    libfreetype6-dev \
    libxml2-dev \
    libexpat1-dev \
    libbz2-dev \
    libgmp3-dev \
    libldap2-dev \
    unixodbc-dev \
    libsqlite3-dev \
    libaspell-dev \
    libsnmp-dev \
    libpcre3-dev \
    libtidy-dev
# Intall compiler tools
RUN apt-get install -y bison
# Install PHP extensions
RUN docker-php-ext-install \
    mbstring \
    mcrypt \
    pdo_mysql \
    curl \
    json \
    intl \
    gd \
    xml \
    zip \
    bz2 \
    opcache
# Install & enable Xdebug for code coverage reports
RUN pecl install xdebug
RUN docker-php-ext-enable xdebug
# Enable URL rewrite
RUN a2enmod rewrite
# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

WORKDIR /var/www/html/
