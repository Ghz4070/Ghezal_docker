FROM php:7.2-apache

LABEL maintainer="Ghezal Ilies"

ENV APACHE_DOCUMENT_ROOT /application

RUN sed -ri -e 's!/var/www/html!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/sites-available/*.conf

RUN sed -ri -e 's!/var/www/!${APACHE_DOCUMENT_ROOT}!g' /etc/apache2/apache2.conf /etc/apache2/conf-available/*.conf 

RUN apt-get update && \
	docker-php-ext-install pdo_mysql 

RUN useradd ilies

RUN usermod --non-unique --uid 1000 www-data && \
	groupmod --non-unique --gid 1000 www-data