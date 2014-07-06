FROM ubuntu:14.04
MAINTAINER Xabier Larrakoetxea <slok69@gmail.com>

# Install nginx
RUN sudo apt-get update
RUN sudo apt-get install -y nginx

VOLUME ["/etc/nginx", "/var/log/nginx"]
EXPOSE 80 443

COPY nginx.conf /etc/nginx/nginx.conf

# This image should only run nginx, don't allow command overwrite
ENTRYPOINT ["nginx"]