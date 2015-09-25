FROM mereghost/archlinux:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-05-29

RUN pacman -Syu memcached --noconfirm

EXPOSE 11211
ENTRYPOINT ["/usr/bin/memcached", "-v"]
