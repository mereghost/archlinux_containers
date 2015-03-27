FROM mereghost/archlinux:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-03-27

RUN pacman -Syu memcached --noconfirm

EXPOSE 11211
ENTRYPOINT ["/usr/bin/memcached", "-v"]
