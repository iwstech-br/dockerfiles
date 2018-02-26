FROM httpd:2.4
MAINTAINER Anderson Junqueira (anderson.junqueira@gmail.com)

ARG BINARY_FILE
ENV ENVIRONMENT=prod

RUN apt-get update 
RUN apt-get install -y unzip

# PASSAR O PARAMETRO DO ARQUIVO BIN DO JAVA
COPY ${BINARY_FILE} /opt/package.zip
RUN unzip /opt/package.zip -d /opt
RUN rm -R /usr/local/apache2/htdocs/*
RUN cp -r /opt/build/* /usr/local/apache2/htdocs

