FROM php:8.2-apache

# Enable Apache modules
RUN a2enmod rewrite

# Copy custom VirtualHost config
COPY laravel.conf /etc/apache2/sites-available/laravel.conf

# Enable it and disable default
RUN a2dissite 000-default.conf && \
	a2ensite laravel.conf

# Set working directory
WORKDIR /var/www/html

# Install PHP extensions Laravel needs
RUN apt-get update && apt-get install -y \
	libzip-dev zip unzip git libsqlite3-dev \
	&& docker-php-ext-install pdo pdo_mysql pdo_sqlite zip \
	&& docker-php-ext-enable pdo_sqlite

# Install Composer
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer
