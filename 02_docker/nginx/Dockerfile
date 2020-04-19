FROM ubuntu:latest
RUN apt-get update
RUN apt-get install nginx git -y
RUN rm -rfv /var/www/html/*
RUN git clone https://github.com/diranetafen/static-website-example.git
RUN cp -R /static-website-example/* /home/
RUN cp -R /static-website-example/* /var/www/html/
#ADD /static-website-example /var/www/html/
RUN sed -i 's/80 default_server/8080 default_server/g' /etc/nginx/sites-enabled/default

EXPOSE 8080
ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
