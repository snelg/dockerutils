FROM alpine

RUN apk --no-cache add php7 php7-session php7-pdo_mysql php7-pdo_sqlite php7-pdo_pgsql php7-openssl ca-certificates \
  && mkdir /app \
  && php -r "copy('https://www.adminer.org/latest-en.php', 'app/index.php');" \
  && apk --purge del php7-openssl ca-certificates \
  && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

EXPOSE 80
CMD ["php", "-S", "0.0.0.0:80", "-t", "/app"]

