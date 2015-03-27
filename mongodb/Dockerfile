FROM mereghost/archlinux_devel:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-01-16

RUN pacman -S --noconfirm --needed mongodb

EXPOSE 27017

USER mongodb
ENTRYPOINT ["/usr/bin/mongod", "-f", "/etc/mongodb.conf"]
