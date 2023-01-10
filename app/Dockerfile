FROM ubuntu:latest

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install -y tzdata apt-utils
ENV TZ "Europe/Amsterdam"
ENV APACHE_RUN_DIR "/run/apache2"
ENV APACHE_PID_FILE "/run/apache2.pid'"
ENV APACHE_RUN_USER "nobody"
ENV APACHE_RUN_GROUP "nogroup"
ENV APACHE_LOG_DIR "/var/log/apache2/"
RUN echo "Europe/Amsterdam" > /etc/timezone && dpkg-reconfigure --frontend noninteractive tzdata
RUN apt-get install -y apache2 php libapache2-mod-php php-redis apache2-utils
COPY ./*.php /var/www/html/
COPY ./php.ini /etc/php/7.4/apache2/php.ini
COPY ./php-8.1.ini /etc/php/8.1/apache2/php.ini
EXPOSE 80
CMD ["apache2ctl", "-D", "FOREGROUND"]

