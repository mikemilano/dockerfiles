Based on the ubuntu 12.04 image.

All files in etc will be copied to /etc.

The default host root is set to /srv/www. The srv directory
will be added to the image when it is built.

/etc/php5/fpm/pool.d/www.conf is modified to support
custom environment variables.

ENVIRONMENT (i.e. dev, test, live)
DB_HOST
DB_NAME
DB_USER
DB_PASS

These can be set when docker is run, and retreived from php inside the $_SERVER array.

$ docker run -e DB_HOST=db1 -e DB_NAME=mydb -e DB_USER=myuser -e DB_PASS=mypass mmilano/nginx
