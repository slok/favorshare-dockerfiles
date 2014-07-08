FROM busybox
MAINTAINER Xabier Larrakoetxea <slok69@gmail.com>


# Create data directory
RUN mkdir /data

# postgres UID = 102 & GID = 106
RUN chown 102:106 /data
RUN chmod 700 /data

# Create
VOLUME /data