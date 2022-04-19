<<<<<<< HEAD
FROM php:7.4.29-alpine

# Install dev dependencies
RUN apk add --no-cache --virtual .build-deps \
    $PHPIZE_DEPS \
    curl-dev \
    imagemagick-dev \
    libtool \
    libxml2-dev \
    postgresql-dev \
    sqlite-dev

# Install production dependencies
RUN apk add --no-cache \
    bash \
    curl \
    g++ \
    gcc \
    git \
    imagemagick \
    xvfb  \
    firefox  \
    dbus  \
    ttf-dejavu \
    libc-dev \
    libpng-dev \
    make \
    mysql-client \
    nodejs \
    nodejs-npm \
=======
FROM php:7.4.29-alpine

# Add docker-php-extension-installer script
ADD https://github.com/mlocati/docker-php-extension-installer/releases/latest/download/install-php-extensions /usr/local/bin/

# Install dependencies
RUN apk add --no-cache \
    bash \
    curl \
    freetype-dev \
    g++ \
    gcc \
    git \
    icu-dev \
    icu-libs \
    libc-dev \
    libzip-dev \
    make \
    mysql-client \
    nodejs \
    npm \
    oniguruma-dev \
>>>>>>> 92adf026076a7aac3d5d8a6fc2154dac6eb5ea9b
    yarn \
    openssh-client \
    postgresql-libs \
    rsync \
<<<<<<< HEAD
    zlib-dev \
    libzip-dev

# Install PECL and PEAR extensions
RUN pecl install \
    imagick

# Install and enable php extensions
RUN docker-php-ext-enable \
    imagick
RUN docker-php-ext-configure zip --with-libzip
RUN docker-php-ext-install \
    curl \
    iconv \
    mbstring \
    pdo \
    pdo_mysql \
    pdo_pgsql \
    pdo_sqlite \
    pcntl \
    tokenizer \
    xml \
    gd \
    zip \
    bcmath

# Install composer
ENV COMPOSER_HOME /composer
ENV PATH ./vendor/bin:/composer/vendor/bin:$PATH
ENV COMPOSER_ALLOW_SUPERUSER 1
RUN curl -s https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer
=======
    zlib-dev

# Install php extensions
RUN chmod +x /usr/local/bin/install-php-extensions && \
    install-php-extensions \
    @composer \
    redis-stable \
    imagick-stable \
    xdebug-stable \
    bcmath \
    calendar \
    exif \
    gd \
    intl \
    pdo_mysql \
    pdo_pgsql \
    pcntl \
    soap \
    zip

# Add local and global vendor bin to PATH.
ENV PATH ./vendor/bin:/composer/vendor/bin:/root/.composer/vendor/bin:/usr/local/bin:$PATH
>>>>>>> 92adf026076a7aac3d5d8a6fc2154dac6eb5ea9b

# Install PHP_CodeSniffer
RUN composer global require "squizlabs/php_codesniffer=*"

<<<<<<< HEAD
# Cleanup dev dependencies
RUN apk del -f .build-deps

# fix work iconv library with alphine
RUN apk add --no-cache --repository http://dl-cdn.alpinelinux.org/alpine/edge/community/ --allow-untrusted gnu-libiconv
ENV LD_PRELOAD /usr/lib/preloadable_libiconv.so php

=======
>>>>>>> 92adf026076a7aac3d5d8a6fc2154dac6eb5ea9b
# Setup working directory
WORKDIR /var/www
