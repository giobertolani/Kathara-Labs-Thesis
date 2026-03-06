FROM kathara/base
LABEL org.opencontainers.image.authors="Kathara Team <contact@kathara.org>"

ARG DEBIAN_FRONTEND="noninteractive"
RUN apt update
RUN apt upgrade -y

# one image for ettercap and dhcp
RUN apt install -y dnsmasq
RUN apt install -y ettercap-text-only
	
RUN mkdir -p /tmp && chmod 1777 /tmp
COPY dnsmasq.conf /etc/dnsmasq.conf

RUN apt clean && \
	rm -rf /tmp/* /var/lib/apt/lists/* /var/tmp/*

