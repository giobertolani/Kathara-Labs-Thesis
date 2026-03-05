FROM kathara/base

RUN apt update
RUN apt upgrade -y

RUN apt install -y dnsmasq
RUN apt install -y isc-dhcp-relay
	
RUN mkdir -p /tmp && chmod 1777 /tmp
COPY dnsmasq.conf /etc/dnsmasq.conf

