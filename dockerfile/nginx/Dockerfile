FROM debian:jessie

MAINTAINER Gundamkid <ngoanhtuan245@gmail.com>

RUN apt-get update && apt-get install -y \
    nginx

ADD nginx.conf /etc/nginx/
ADD employee_management.conf /etc/nginx/sites-available/

RUN ln -s /etc/nginx/sites-available/employee_management.conf /etc/nginx/sites-enabled/
RUN rm /etc/nginx/sites-enabled/default

RUN echo "upstream php-upstream { server php7:9000; }" > /etc/nginx/conf.d/upstream.conf

RUN usermod -u 1000 www-data

CMD ["nginx"]

EXPOSE 80
EXPOSE 443