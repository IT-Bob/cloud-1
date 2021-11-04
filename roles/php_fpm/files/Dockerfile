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

COPY www.conf /etc/php8/php-fpm.d/

CMD ["php-fpm8", "-F"]
