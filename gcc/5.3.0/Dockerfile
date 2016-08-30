FROM alpine:3.4

RUN apk add --update --no-cache \
        bash p7zip openssl ca-certificates \
        g++=5.3.0-r0 \
        build-base autoconf automake \
        libtool zlib-dev bzip2-dev lzo-dev openssl-dev \
 && update-ca-certificates \
 && rm -rf /var/cache/apk/*
