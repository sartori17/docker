FROM php:7.1.3-apache
MAINTAINER sartori.felipe@gmail.com

RUN a2enmod rewrite
RUN apt-get update && apt-get install -y vim
RUN docker-php-ext-install pdo pdo_mysql
RUN apt-get install -y xclip

WORKDIR /root
COPY addvhost_docker.sh /root/addvhost_docker.sh
COPY vhost.skeleton.docker.conf /root/vhost.skeleton.docker.conf

RUN /bin/bash -c "./addvhost_docker.sh -u adminer.dev -d adminer.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u curso_pdo.dev -d curso_pdo.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u curso_poo.dev -d curso_poo.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u financas.dev -d financas.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u new_site.dev -d new_site.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u sitesimples.dev -d sitesimples.dev/src"
RUN /bin/bash -c "./addvhost_docker.sh -u son_poo.dev -d son_poo.dev/src"

WORKDIR /var/www/html