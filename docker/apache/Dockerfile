FROM debian

LABEL maintainer="davidgarciavalero@gmail.com"

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y apache2 && apt-get clean

RUN a2enmod rewrite

RUN mkdir -p /var/log/apache2/custom

WORKDIR /var/www/html

EXPOSE 80

CMD ["apachectl", "-D", "FOREGROUND"]
