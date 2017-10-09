FROM alpine

RUN apk --no-cache add php7 php7-session php7-pdo_mysql php7-pdo_sqlite php7-pdo_pgsql wget ca-certificates \
  && mkdir /app \
  && wget -O /app/index.php https://www.adminer.org/latest-en.php \
  && apk --purge del wget \
  && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

EXPOSE 80
CMD ["php", "-S", "0.0.0.0:80", "-t", "/app"]

