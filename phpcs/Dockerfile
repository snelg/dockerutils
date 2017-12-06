FROM alpine

ENV PHPCS_VERSION=2.9.1

RUN apk --no-cache add php7 php7-ctype php7-phar php7-zlib php7-tokenizer php7-simplexml php7-openssl ca-certificates \
    && php -r "copy('https://github.com/squizlabs/PHP_CodeSniffer/releases/download/$PHPCS_VERSION/phpcs.phar', '/usr/local/bin/phpcs');" \
    && chmod +x /usr/local/bin/phpcs \
    && apk --purge del php7-openssl ca-certificates \
    && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

VOLUME ["/workspace"]
WORKDIR /workspace

ENTRYPOINT ["phpcs"]
CMD ["--version"]

