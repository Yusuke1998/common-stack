FROM php:7.4-apache

RUN apt-get update && apt-get upgrade -y
RUN apt-get install -y zlib1g-dev libpng-dev && rm -rf /var/lib/apt/lists/*
RUN docker-php-ext-install mysqli pdo pdo_mysql gd && docker-php-ext-enable mysqli pdo pdo_mysql gd

ADD ./devsetup.conf /etc/apache2/conf-available/
ADD ./devsetup.ini /usr/local/etc/php/conf.d/

RUN a2enconf devsetup
RUN a2enmod rewrite
RUN service apache2 restart
