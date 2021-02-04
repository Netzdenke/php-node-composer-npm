FROM php:7.4

RUN apt-get update \
    && apt-get install -y curl apt-transport-https git build-essential libssl-dev wget unzip bzip2 libbz2-dev zlib1g-dev \
    libfontconfig libfreetype6-dev libjpeg62-turbo-dev libpng-dev libicu-dev libxml2-dev libldap2-dev libmcrypt-dev \
    python-pip fabric jq gnupg libzip-dev \
    && apt-get clean

RUN curl -sL https://deb.nodesource.com/setup_15.x | bash - \
    && apt-get update \
    && apt-get install -y nodejs \
    && npm install -g npm \
    && npm install --global gulp-cli

ENV COMPOSER_ALLOW_SUPERUSER 1
RUN rm -f /usr/local/bin/composer \
    && curl -s -f -L -o /usr/local/bin/composer https://getcomposer.org/download/2.0.9/composer.phar \
    && chmod +x /usr/local/bin/composer

RUN docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) \
      bcmath \
      bz2 \
      gd \
      gettext \
      intl \
      zip