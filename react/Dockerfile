FROM ubuntu
MAINTAINER Anderson Junqueira (anderson.junqueira@gmail.com)

ARG BINARY_FILE

RUN apt-get update 
RUN apt-get install -y apache2 unzip

# PASSAR O PARAMETRO DO ARQUIVO BIN DO JAVA
RUN rm -R /var/www/html/*
COPY ${BINARY_FILE} /opt/package.zip
RUN unzip /opt/package.zip -d /var/www/html

# EXPOR A PORTA
EXPOSE 80
