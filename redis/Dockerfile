FROM ubuntu:14.04
MAINTAINER Xabier Larrakoetxea <slok69@gmail.com>

# Update repos
RUN apt-get update

# Install Redis
RUN apt-get install -y redis-server

# Expose Redis port 6379
EXPOSE 6379

CMD ["/usr/bin/redis-server"]
