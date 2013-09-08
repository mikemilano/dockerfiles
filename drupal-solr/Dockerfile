FROM ubuntu:12.04

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y -q iputils-ping wget curl tree vim

RUN apt-get install -y -q tomcat6

ADD . /src
RUN cp -rf /src/files/* /
RUN rm -rf /src

EXPOSE 8983
CMD ["/etc/docker/drupal-solr-start"]
