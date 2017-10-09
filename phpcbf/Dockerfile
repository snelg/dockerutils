FROM alpine

ENV PHPCBF_VERSION=2.8.1

RUN apk --no-cache add php7 php7-phar php7-zlib php7-tokenizer php7-simplexml patch wget ca-certificates \
    && wget -O /usr/local/bin/phpcbf https://github.com/squizlabs/PHP_CodeSniffer/releases/download/$PHPCBF_VERSION/phpcbf.phar \
    && chmod +x /usr/local/bin/phpcbf \
    && apk --purge del wget ca-certificates \
    && rm -rf /var/cache/apk/* /var/tmp/* /tmp/*

VOLUME ["/workspace"]
WORKDIR /workspace

ENTRYPOINT ["phpcbf"]
CMD ["--version"]

