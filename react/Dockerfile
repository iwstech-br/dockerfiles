FROM ubuntu
MAINTAINER Anderson Junqueira (anderson.junqueira@gmail.com)

ARG BINARY_FILE

RUN apt-get update 
RUN apt-get install -y apache2 unzip

# PASSAR O PARAMETRO DO ARQUIVO BIN DO JAVA
COPY ${BINARY_FILE} /opt/package.zip
RUN unzip /opt/package.zip -d /opt
RUN rm -R /var/www/html/*
RUN cp -r /opt/build/* /var/www/html

# EXPOR A PORTA
EXPOSE 80
