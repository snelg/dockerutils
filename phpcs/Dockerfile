FROM alpine

ENV PHPCS_VERSION=2.8.1

RUN apk --no-cache add php7 php7-phar php7-zlib php7-tokenizer php7-simplexml wget ca-certificates \
    && wget -O /usr/local/bin/phpcs https://github.com/squizlabs/PHP_CodeSniffer/releases/download/$PHPCS_VERSION/phpcs.phar \
    && chmod +x /usr/local/bin/phpcs \
    && apk --purge del wget ca-certificates \
    && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

VOLUME ["/workspace"]
WORKDIR /workspace

ENTRYPOINT ["phpcs"]
CMD ["--version"]

