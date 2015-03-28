FROM mereghost/archlinux_devel:latest
MAINTAINER Marcello 'mereghost' Rocha
ENV REFRESHED_AT 2015-03-27

RUN pacman -S --noconfirm --needed --asdeps erlang-nox
RUN useradd -mg users packager

ENV RABBITMQ_VERSION 3.5.0

ADD https://aur.archlinux.org/packages/ra/rabbitmq/rabbitmq.tar.gz /tmp/
RUN chown packager /tmp/rabbitmq.tar.gz

USER packager
RUN gpg --keyserver pgpkeys.mit.edu --recv-key F7B8CEA6056E8E56 && tar -C /tmp -xvf /tmp/rabbitmq.tar.gz && cd /tmp/rabbitmq && makepkg -s --noconfirm 

USER root
RUN pacman -U /tmp/rabbitmq/rabbitmq-${RABBITMQ_VERSION}-1-x86_64.pkg.tar.xz --noconfirm

USER rabbitmq
RUN echo "[{rabbit, [{loopback_users, []}]}]." > /etc/rabbitmq/rabbitmq.config && rabbitmq-plugins enable --offline rabbitmq_management > /dev/null

EXPOSE 5672 15672 25672

ENTRYPOINT ["/usr/bin/rabbitmq-server"]
