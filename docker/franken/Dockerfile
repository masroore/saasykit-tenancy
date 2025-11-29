FROM dunglas/frankenphp AS base

ENV TZ=Asia/Dhaka
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN install-php-extensions \
	redis \
	bcmath \
    msgpack \
    xml \
    igbinary \
    memcached \
    pcov \
    imagick \
    fileinfo \
	gd \
	zip \
	opcache \
	intl \
	pcntl

ENV SERVER_NAME=:80

FROM base AS production

RUN mv "$PHP_INI_DIR/php.ini-production" "$PHP_INI_DIR/php.ini"

COPY . /app
