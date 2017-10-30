FROM tetraweb/php:7.1

# Update and Install Packages
RUN apt-get update -y && apt-get install -y \
    unzip \
    libfontconfig \
    libicu-dev \
    libzip-dev \
    jq

RUN docker-php-ext-install intl zip

RUN php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
RUN php composer-setup.php
RUN php -r "unlink('composer-setup.php');"
