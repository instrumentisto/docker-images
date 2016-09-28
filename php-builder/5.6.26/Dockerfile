FROM php:5.6.26-alpine


RUN apk add --update --no-cache \
        bash git p7zip openssl ca-certificates \
 && update-ca-certificates \
 && rm -rf /var/cache/apk/*

# Install Composer (https://getcomposer.org/download/)
RUN wget -O /tmp/composer-setup.php \
         https://getcomposer.org/installer \
 && php -r "if (hash_file('SHA384', '/tmp/composer-setup.php') === 'e115a8dc7871f15d853148a7fbac7da27d6c0030b848d9b3dc09e2a0388afed865e6a3d6b3c0fad45c48e2b5fc1196ae') { echo 'Installer verified'.PHP_EOL; } else { echo 'Installer corrupt'.PHP_EOL; die(1); }" \
 && php /tmp/composer-setup.php --install-dir=/usr/bin \
                                --filename=composer \
                                --version=1.2.1 \
 && rm -rf /tmp/composer-setup.php
