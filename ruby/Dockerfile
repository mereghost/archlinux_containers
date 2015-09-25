FROM mereghost/archlinux_devel:2015-07-29
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-08-20

RUN pacman -Sy ruby git --noconfirm --needed
RUN echo 'gem: --no-rdoc --no-ri' >> /etc/gemrc
RUN gem install bundler
