FROM debian
MAINTAINER Valentin Efremov <Shadow77746@gmail.com>
RUN apt-get update
RUN apt-get upgrade
RUN apt-get install -y nginx 
RUN apt-get clean
RUN rm -rf /var/www/*
RUN mkdir -p /var/www/company.com/img
ADD index.html /var/www/company.com/index.html
ADD images2.jpg /var/www/company.com/img/images2.jpg
RUN chmod -R 754 /var/www/company.com
RUN useradd Valentin
RUN groupadd Efremov
RUN usermod -a -G Efremov Valentin
RUN chown -R Valentin:Efremov /var/www/company.com
RUN sed -i 's|/var/www/html|/var/www/company.com|g' /etc/nginx/sites-enabled/default
RUN sed -i 's|user www-data;|user Valentin;|g' /etc/nginx/nginx.conf
