FROM mereghost/archlinux:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2014-12-10

RUN pacman -Syu base-devel --noconfirm --needed
RUN pacman -S ruby git --noconfirm --needed
ENV PATH /.gem/ruby/2.1.0/bin:$PATH
RUN echo 'gem: --no-rdoc --no-ri' >> /etc/gemrc
RUN gem install bundler
