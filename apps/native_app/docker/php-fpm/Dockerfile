FROM php:8.2-fpm

RUN apt-get update && \
    apt-get install -y zip curl libcurl3-dev libzip-dev libpng-dev libonig-dev libxml2-dev
    # libonig-dev is needed for oniguruma which is needed for mbstring

# Installing additional PHP modules
RUN docker-php-ext-install curl gd mbstring mysqli pdo pdo_mysql xml opcache

# Install and configure ImageMagick
#RUN apt-get install -y libmagickwand-dev
#RUN pecl install imagick
#RUN docker-php-ext-enable imagick
#RUN apt-get purge -y libmagickwand-dev
RUN chown -R www-data:www-data /var/www \
    && chmod 755 /var/www
# Install Composer so it's available
RUN curl -sS httdockps://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer