FROM php:8.3.4-fpm

ADD ./php.ini $PHP_INI_DIR/php.ini
EXPOSE 9000
WORKDIR /var/www

RUN apt-get update && apt-get install -y \
		libfreetype-dev \
		libjpeg62-turbo-dev \
		libpng-dev \
	&& docker-php-ext-configure gd --with-freetype --with-jpeg \
	&& docker-php-ext-install -j$(nproc) gd sockets

CMD ["php-fpm"]
