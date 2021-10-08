# ft_php-fpm

# Use alpine linux as base image
FROM alpine:latest

# update and upgrade packages
# and install php-fpm
RUN apk update\
  && apk upgrade\
  && apk add php8-fpm

# update php-fpm config
RUN sed -i 's/^listen = 127.0.0.1:9000$/listen = 0.0.0.0:9000/' /etc/php8/php-fpm.d/www.conf

CMD ["php-fpm8", "-F"]
