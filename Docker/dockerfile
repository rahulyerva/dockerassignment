FROM jmcarbo/nginx-php-fpm
MAINTAINER Rahul Reddy Yerva
RUN sed -i 's/#server_name localhost/server_name localhost/g' /etc/nginx/sites-available/default.conf
RUN chmod 644 /etc/nginx/sites-available/default.conf
ADD commands.sh /commands.sh
CMD sh /commands.sh
EXPOSE 80
WORKDIR /
