FROM mereghost/archlinux:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-07-29

RUN pacman -Syu --noconfirm elasticsearch 

USER elasticsearch

EXPOSE 9200 9300 5428/udp
ENTRYPOINT ["elasticsearch"]



