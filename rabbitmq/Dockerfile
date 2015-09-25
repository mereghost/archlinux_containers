FROM mereghost/archlinux:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-09-25
RUN pacman -S rabbitmq --noconfirm

USER rabbitmq
RUN echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config && rabbitmq-plugins enable --offline rabbitmq_management > /dev/null

EXPOSE 5672 15672 25672

ENTRYPOINT ["/usr/bin/rabbitmq-server"]
