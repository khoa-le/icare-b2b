FROM php:7.0-fpm
MAINTAINER Gundamkid <ngoanhtuan245@gmail.com>

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
RUN composer --version

RUN apt-get update && apt-get install -y \
    git \
    unzip

# Set timezone
RUN rm /etc/localtime
RUN ln -s /usr/share/zoneinfo/UTC /etc/localtime
RUN "date"

#RUN docker-php-ext-install pdo pdo_mysql intl mcrypt

RUN echo 'alias sf="php app/console"' >> ~/.bashrc

RUN usermod -u 1000 www-data
