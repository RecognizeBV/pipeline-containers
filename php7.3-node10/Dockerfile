FROM php:7.3
RUN apt-get update \
    && apt-get install -y zip libzip-dev git libicu-dev \
    && docker-php-ext-install pdo pdo_mysql zip intl \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# Install Node
ENV NPM_CONFIG_LOGLEVEL notice
ENV NODE_VERSION 10.16.3

RUN curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz" \
    && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1 \
    && rm "node-v$NODE_VERSION-linux-x64.tar.xz" \
    && ln -s /usr/local/bin/node /usr/local/bin/nodejs
