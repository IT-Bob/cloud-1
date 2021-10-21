# ft_php-fpm

# use alpine linux as base image
FROM alpine:latest

# update and upgrade packages
# and install php-fpm
RUN apk update\
  && apk upgrade\
  && apk add php8-fpm\
    php8-iconv\
    php8-mysqli\
    php8-session\
    php8-xml

# update php-fpm config
RUN sed -i 's/^listen = 127.0.0.1:9000$/listen = 0.0.0.0:9000/' /etc/php8/php-fpm.d/www.conf

CMD ["php-fpm8", "-F"]
