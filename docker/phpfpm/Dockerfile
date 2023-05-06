# FROM php:7-fpm

# RUN apt-get update && apt-get install -y \
#   libjpeg-dev \
#   libpng-dev

# RUN docker-php-ext-install \
#   gd \
#   opcache \
#   pdo_mysql

# WORKDIR /srv/www

FROM php:7-fpm

RUN apt-get update && apt-get install -y \
  libjpeg-dev \
  libpng-dev \
  libpq-dev \
  libicu-dev \
  libxml2-dev \
  libzip-dev \
  unzip \
  git \
  curl \
  vim

# Install PHP extensions
RUN docker-php-ext-configure gd --with-jpeg \
    && docker-php-ext-install \
      bcmath \
      gd \
      opcache \
      intl \
      pdo_mysql \
      mysqli \
      soap \
      zip \
      pcntl

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Copy custom PHP configuration
# COPY php.ini /usr/local/etc/php/conf.d/custom-php.ini
COPY php-fpm.conf /usr/local/etc/php/conf.d/
COPY php.ini /usr/local/etc/php/

WORKDIR /srv/www

# Install Drupal Console globally
RUN curl https://drupalconsole.com/installer -L -o drupal.phar && \
    mv drupal.phar /usr/local/bin/drupal && \
    chmod +x /usr/local/bin/drupal

# Change user ID and group ID to match host user and group
ARG USER_ID=1000
ARG GROUP_ID=1000
RUN usermod -u $USER_ID www-data && groupmod -g $GROUP_ID www-data

CMD ["php-fpm"]