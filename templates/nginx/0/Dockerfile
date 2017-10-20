FROM nginx:latest
MAINTAINER Nikita Volkov <litebackend@gmail.com>

RUN rm /etc/nginx/nginx.conf /etc/nginx/mime.types
COPY nginx.conf /etc/nginx/nginx.conf
COPY mime.types /etc/nginx/mime.types
RUN mkdir /etc/nginx/ssl
COPY default.conf /etc/nginx/sites-enabled/default.conf
COPY default-ssl.conf /etc/nginx/sites-available/default-ssl.conf

WORKDIR /opt/app
# expose both the HTTP (80) and HTTPS (443) ports
EXPOSE 80

COPY docker-entrypoint.sh /etc/app/docker-entrypoint.sh

RUN ["chmod", "+x", "/etc/app/docker-entrypoint.sh"]

ENTRYPOINT ["/etc/app/docker-entrypoint.sh"]
