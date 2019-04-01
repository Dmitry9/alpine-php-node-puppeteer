FROM alpine:latest

# Install packages
RUN apk --no-cache add git nginx curl openssh

#Install php
RUN apk --no-cache add php7 php7-fpm php7-mysqli php7-json php7-openssl php7-curl \
            php7-zlib php7-xml php7-phar php7-intl php7-dom php7-xmlreader php7-ctype \
            php7-mbstring php7-gd php7-common php7-session php7-zip php7-gettext \
            php7-fileinfo php7-bcmath php7-tokenizer php7-pdo_mysql

# Install node and npm
RUN apk add --update nodejs nodejs-npm && npm i -g yarn

RUN mkdir /run/nginx