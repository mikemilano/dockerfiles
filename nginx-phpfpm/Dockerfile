FROM ubuntu:12.04

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y -q iputils-ping wget curl tree vim

ADD . /src

RUN apt-get install -y -q nginx
RUN echo "daemon off;" >> /etc/nginx/nginx.conf

RUN apt-get install -y -q php5-fpm php5-cli php5-mcrypt php5-mysqlnd php5-xdebug php-apc

RUN rm /etc/nginx/sites-enabled/default

#RUN cp /src/etc/nginx/conf.d/default.conf /etc/nginx/conf.d/
RUN cp -rf /src/etc/* /etc/
RUN cp -r /src/srv /

EXPOSE 80
CMD /etc/init.d/php5-fpm start; /usr/sbin/nginx
