FROM eboraas/apache:latest
MAINTAINER Ed Boraas <ed@boraas.ca>


RUN apt-get update && apt-get -y install apache2 libapache2-mod-php5 && apt-get clean && rm -rf /var/lib/apt/lists/*

ENV APACHE_RUN_USER www-data
ENV APACHE_RUN_GROUP www-data
ENV APACHE_LOG_DIR /var/log/apache2

RUN /usr/sbin/a2ensite default-ssl
RUN /usr/sbin/a2enmod ssl


EXPOSE 80
EXPOSE 443


COPY ./app.conf /etc/apache2/sites-available/app.conf
RUN a2ensite app.conf
RUN a2dissite 000-default.conf
RUN a2dissite default-ssl.conf

RUN mkdir /var/www/html/web
COPY ./index.php /var/www/html/web/index.php


CMD ["/usr/sbin/apache2ctl","-DFOREGROUND"]