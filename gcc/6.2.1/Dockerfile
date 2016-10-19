FROM alpine:edge

RUN apk add --update --no-cache \
        bash p7zip openssl ca-certificates \
        g++=6.2.1-r0 \
        build-base autoconf automake \
        libtool zlib-dev bzip2-dev lzo-dev openssl-dev \
 && update-ca-certificates \
 && rm -rf /var/cache/apk/*
