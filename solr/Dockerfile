FROM ubuntu:12.04

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y -q iputils-ping wget curl tree vim

RUN apt-get install -y -q solr-tomcat tomcat6-admin

ADD . /src
RUN cp -rf /src/files/* /
RUN rm -rf /src

EXPOSE 8080
#CMD /etc/init.d/php5-fpm start; /usr/sbin/nginx
