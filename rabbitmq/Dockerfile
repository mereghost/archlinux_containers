FROM mereghost/archlinux_devel:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-01-16

RUN pacman -S --noconfirm --needed --asdeps erlang-nox
RUN useradd -g users packager

ADD rabbitmq.tar.gz /tmp/
RUN chown -R packager /tmp/rabbitmq
USER packager
RUN cd /tmp/rabbitmq && makepkg -s --noconfirm 
USER root
RUN pacman -U /tmp/rabbitmq/rabbitmq-3.4.3-1-x86_64.pkg.tar.xz --noconfirm

USER rabbitmq
RUN rabbitmq-plugins enable rabbitmq_management
RUN echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config

EXPOSE 5672 15672 25672

ENTRYPOINT ["/usr/bin/rabbitmq-server"]
