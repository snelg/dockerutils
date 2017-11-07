FROM alpine

ENV PHPCBF_VERSION=2.9.1

RUN apk --no-cache add php7 php7-phar php7-zlib php7-tokenizer php7-simplexml php7-openssl ca-certificates patch \
    && php -r "copy('https://github.com/squizlabs/PHP_CodeSniffer/releases/download/$PHPCBF_VERSION/phpcbf.phar', '/usr/local/bin/phpcbf');" \
    && chmod +x /usr/local/bin/phpcbf \
    && apk --purge del php7-openssl ca-certificates \
    && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

VOLUME ["/workspace"]
WORKDIR /workspace

ENTRYPOINT ["phpcbf"]
CMD ["--version"]

