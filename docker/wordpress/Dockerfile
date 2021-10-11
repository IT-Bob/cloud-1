# ft_wordpress

# Use ft_wordpress as base image
FROM ft_nginx:latest

# update and upgrade packages
RUN apk update\
  && apk upgrade

# copy and extract wordpress sources to the container
ADD wordpress-latest.tar.gz /usr/share/nginx/

# copy nginx configuration file for wordpress
COPY wordpress.conf /etc/nginx/conf.d/

# remove default site and its associate nginx config file
RUN rm -rf /usr/share/nginx/html\
  && rm /etc/nginx/conf.d/default.conf
