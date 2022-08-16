FROM php:fpm-alpine

# Install extensions
RUN docker-php-ext-install pdo_mysql bcmath

# Install Composer
COPY --from=composer /usr/bin/composer /usr/local/bin/composer