FROM php:8.0.13-cli

RUN apt-get update -y && apt-get install -y libmcrypt-dev

RUN curl -sS https://getcomposer.org/installer | php -- \
    &&  mv composer.phar /usr/local/bin/composer

RUN curl -sS https://get.symfony.com/cli/installer | bash \
    &&  mv /root/.symfony5/bin/symfony /usr/local/bin

WORKDIR /app
COPY . /app

RUN composer install

EXPOSE 8000
CMD php bin/console server:run 0.0.0.0:8000