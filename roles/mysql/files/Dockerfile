# ft_mysql

# use alpine linux as base image
FROM debian:buster

# update and upgrade packages
# and install prerequisites
RUN apt-get update\
  && apt-get upgrade -y\
  && apt-get install -y\
    gnupg\
    lsb-release

# copy mysql PGP key
COPY mysql.key /tmp/

# Add MySQL PGP key,
# add MySQL apt repository,
# update repositories, install mysql and remove PGP file
RUN apt-key add /tmp/mysql.key\
  && echo "deb http://repo.mysql.com/apt/$(lsb_release -is | tr [A-Z] [a-z])/ $(lsb_release -cs) mysql-8.0" > /etc/apt/sources.list.d/mysql.list\
  && apt-get update\
  && DEBIAN_FRONTEND=noninteractive apt-get install -y mysql-server\
  && rm /tmp/mysql.key

CMD ["mysqld_safe"]
