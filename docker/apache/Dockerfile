FROM debian

LABEL maintainer="davidgarciavalero@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y apache2 && apt-get clean

RUN a2enmod rewrite

RUN mkdir -p /var/log/apache2/custom

WORKDIR /var/www/html

RUN sed -i 's/80/10000/g' /etc/apache2/ports.conf \
 && sed -i 's/:80/:10000/g' /etc/apache2/sites-available/000-default.conf

COPY app/public_html/ /var/www/html/

EXPOSE 10000


CMD ["apachectl", "-D", "FOREGROUND"]
