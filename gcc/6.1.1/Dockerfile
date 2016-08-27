FROM alpine:edge

RUN apk add --update --no-cache \
        bash openssl ca-certificates \
        g++=6.1.1-r0 \
        make autoconf automake build-base \
        libtool zlib-dev bzip2-dev lzo-dev openssl-dev \
 && update-ca-certificates \
 && rm -rf /var/cache/apk/*
