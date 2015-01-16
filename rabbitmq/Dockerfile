FROM mereghost/archlinux_devel:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2014-12-10

RUN pacman -S --needed --asdeps erlang-nox
ADD rabbitmq.tar.gz /tmp/
RUN cd /tmp/rabbitmq && makepkg -s --noconfirm --asroot && pacman -U rabbitmq-3.4.2-1-x86_64.pkg.tar.xz --noconfirm

RUN rabbitmq-plugins enable rabbitmq_management
RUN echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config

EXPOSE 5672 15672 25672

ENTRYPOINT ["/usr/bin/rabbitmq-server"]
