FROM php:8.2-fpm

# Set the working directory in the container to /app
WORKDIR ./app

# Copy the current directory contents into the container at /app
COPY ../.. /app

# Install Symfony and other required PHP extensions
RUN apt-get update && apt-get install -y git \
    libzip-dev \
    && docker-php-ext-configure zip \
    && docker-php-ext-install -j$(nproc) zip
#RUN apt update \
#    && apt install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip \
#    && docker-php-ext-install intl opcache pdo pdo_mysql \
#    && pecl install apcu \
#    && docker-php-ext-enable apcu \
#    && docker-php-ext-configure zip \
#    && docker-php-ext-install zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Symfony CLI
RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony
# Verify the installation
RUN symfony check:req

# Expose port 8000 for PHP-FPM
EXPOSE 8000