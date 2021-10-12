# nginx

# use alpine linux as base image
FROM alpine:latest

# update and upgrade packages
# and install prerequisites
RUN apk update\
  && apk upgrade\
  && apk add\
    ca-certificates\
    curl\
    openssl

# set up nginx apk repository
RUN printf "%s%s%s%s\n" "@nginx " "http://nginx.org/packages/alpine/v" `egrep -o '^[0-9]+\.[0-9]+' /etc/alpine-release` "/main" \
  | tee -a /etc/apk/repositories\
  && curl -so /tmp/nginx_signing.rsa.pub https://nginx.org/keys/nginx_signing.rsa.pub\
  && openssl rsa -pubin -in /tmp/nginx_signing.rsa.pub -text -noout\
  && mv /tmp/nginx_signing.rsa.pub /etc/apk/keys/

# install nginx
RUN apk update\
  && apk add nginx@nginx

# launch nginx to the foreground
CMD ["nginx", "-g", "daemon off;"]
