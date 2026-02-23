FROM kathara/base
LABEL org.opencontainers.image.authors="Kathara Team <contact@kathara.org>"

ARG DEBIAN_FRONTEND="noninteractive"
RUN apt update
RUN apt upgrade -y

RUN apt install -y ettercap-text-only
RUN apt clean && \
	rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp/*
