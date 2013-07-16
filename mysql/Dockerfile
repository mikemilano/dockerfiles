FROM ubuntu:12.04

RUN echo "deb http://archive.ubuntu.com/ubuntu precise main universe" > /etc/apt/sources.list
RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y -q iputils-ping wget curl tree vim

RUN apt-get install -y -q mysql-server mysql-client
# Fix for MySQL on ubuntu in a virtual environment
RUN dpkg-divert --local --rename --add /sbin/initctl
RUN ln -s /bin/true /sbin/initctl 

ADD . /src
RUN cp -rf /src/etc/* /etc/
RUN chown -R mysql.mysql /etc/mysql
#RUN cp -r /src/srv /

EXPOSE 3306
CMD ["/usr/bin/mysqld_safe"]
