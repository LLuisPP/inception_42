FROM debian:bullseye

RUN apt-get update && apt-get -y upgrade \
    && apt-get install -y \
        php-fpm php-mysql \
        mariadb-client \
        curl wget \
        ca-certificates \
        bash \
    && rm -rf /var/lib/apt/lists/*

RUN mkdir -p /var/www/html \
    && chown -R www-data:www-data /var/www/html

RUN curl -o /usr/local/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar \
    && chmod +x /usr/local/bin/wp

COPY tools/entrypoint.sh /usr/local/bin/entrypoint.sh
RUN chmod +x /usr/local/bin/entrypoint.sh

WORKDIR /var/www/html

EXPOSE 9000

ENTRYPOINT ["/usr/local/bin/entrypoint.sh"]

