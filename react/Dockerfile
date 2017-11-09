FROM teamrock/ubuntu:latest

MAINTAINER Anderson Junqueira (anderson.junqueira@gmail.com)

RUN DEBIAN_FRONTEND=noninteractive apt-get update \
    && apt-get install -y --no-install-recommends apache2 unzip \
    && rm -rf /var/lib/apt/lists/*

COPY conf.d/* /etc/apache2/conf-enabled/
RUN rm -rf /etc/apache2/sites-enabled/000-default.conf /var/www/html
RUN a2enmod rewrite
ENV APACHE_RUN_USER     www-data
ENV APACHE_RUN_GROUP    www-data
ENV APACHE_LOG_DIR      /var/log/apache2
env APACHE_PID_FILE     /var/run/apache2.pid
env APACHE_RUN_DIR      /var/run/apache2
env APACHE_LOCK_DIR     /var/lock/apache2
env APACHE_LOG_DIR      /var/log/apache2

# PASSAR O PARAMETRO DO ARQUIVO BIN DO JAVA
COPY ${BINARY_FILE} /opt/package.zip
RUN unzip /opt/package.zip -d /opt
RUN rm -R /var/www/html/*
RUN cp -r /opt/build/* /var/www/html

EXPOSE 80

ENTRYPOINT [ "/usr/sbin/apache2", "-DFOREGROUND" ]
