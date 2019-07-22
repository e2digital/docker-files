FROM php:7.2

# Update and Install Packages
RUN apt-get update -y && apt-get install -y \
    apt-transport-https \
    git \
    gnupg \
    jq \
    libfontconfig \
    libicu-dev \
    libzip-dev \
    unzip \
    zip \
    rsync

RUN docker-php-ext-install intl zip

# Install Composer
RUN curl -sS https://getcomposer.org/installer | php \
    && mv composer.phar /usr/local/bin/ \
    && ln -s /usr/local/bin/composer.phar /usr/local/bin/composer

# Install Node.js & Yarn
RUN curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && curl -sL https://deb.nodesource.com/setup_12.x | bash - \
    && apt-get install -y nodejs build-essential yarn
