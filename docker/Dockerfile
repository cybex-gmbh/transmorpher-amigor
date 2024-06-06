FROM webdevops/php-nginx:8.3

WORKDIR /var/www/html

ENV WEB_DOCUMENT_ROOT /var/www/html/public

COPY . /var/www/html

RUN composer install --no-interaction --no-dev

RUN chmod +x /var/www/html/docker/entryfile.sh
RUN chmod 755 -R /var/www/html/storage
RUN chown -R application:application /var/www/html/storage

RUN apt update
RUN apt install -y default-mysql-client

ENTRYPOINT ["/var/www/html/docker/entryfile.sh"]
