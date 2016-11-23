FROM thimico/alpine

MAINTAINER thimico

RUN apk-install supervisor \
 && apk-install mysql mysql-client \
 && mysql_install_db --user=mysql -ldata=/var/lib/mysql

WORKDIR /mysql

COPY . /mysql
EXPOSE 3306

CMD ["supervisord", "-c", "/mysql/supervisord.conf"]