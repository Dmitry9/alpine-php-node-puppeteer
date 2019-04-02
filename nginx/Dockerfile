FROM alpine:latest

# Install packages
RUN apk --no-cache add git nginx openssh

#Install php
RUN apk --no-cache add php7 php7-fpm php7-mysqli php7-json php7-openssl php7-curl \
    php7-zlib php7-xml php7-phar php7-intl php7-dom php7-xmlreader php7-ctype \
    php7-mbstring php7-gd php7-common php7-session php7-zip php7-gettext \
    php7-fileinfo php7-bcmath php7-tokenizer php7-pdo_mysql

RUN mkdir /run/nginx && mkdir -p /var/lib/php/session && chmod 777 /var/lib/php/session

# Install node and npm
RUN apk add --update nodejs nodejs-npm && npm i -g yarn

# Install chromium
ENV CHROME_BIN="/usr/bin/chromium-browser" \
    PUPPETEER_SKIP_CHROMIUM_DOWNLOAD="true"

RUN apk update && apk upgrade \
    && apk add --no-cache udev ttf-freefont chromium 

RUN mkdir /app && cd /app && yarn add puppeteer@1.10.0

