FROM php:fpm-alpine

# Import extension installer
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/bin/

# Install extensions
RUN docker-php-ext-install pdo_mysql bcmath opcache redis

# Install Composer
COPY --from=composer /usr/bin/composer /usr/local/bin/composer

# Configure PHP
COPY .docker/php.ini $PHP_INI_DIR/conf.d/opcache.ini

# Use the default development configuration
RUN mv $PHP_INI_DIR/php.ini-development $PHP_INI_DIR/php.ini

# Install extra packages
RUN apk --no-cache add bash mysql-client mariadb-connector-c-dev

# Install Bash
#RUN apk --no-cache add bash

# Create user based on provided user ID
ARG HOST_UID
RUN adduser --disabled-password --gecos "" --uid $HOST_UID demo

# Switch to that user
USER demo