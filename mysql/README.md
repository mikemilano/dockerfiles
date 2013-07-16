Based on the ubuntu 12.04 image.

All files in etc/mysql will be copied over.

Currently there's no root password.

A database has been named "app", which is to be used for your app.
When docker runs, bind a directory to /var/lib/mysql/app.

$ docker run mmilano/mysql
