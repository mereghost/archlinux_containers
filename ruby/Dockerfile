FROM mereghost/archlinux_devel:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-01-16

RUN pacman -S ruby git --noconfirm --needed
ENV PATH /.gem/ruby/2.2.0/bin:$PATH
RUN echo 'gem: --no-rdoc --no-ri' >> /etc/gemrc
RUN gem install bundler
