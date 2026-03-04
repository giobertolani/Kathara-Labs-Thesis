# DHCP lab description
Dynamic Host Configuration Protocol (DHCP) = protocol to manage the configuration of nodes when connecting them to the network. Kathará doesn't have by default an image for a DHCP server so you have to build one by yourself before creating and executing the network scenario. I used **dnsmasq** to create the server in order to use it as a DHCP and a DNS server alltogether.

## DHCP1 - one LAN
This lab is composed by three hosts and a DHCP server, all of them belonging to the same LAN. H1 and H2 are client with pooled addresses whereas H3 has a fixed address: in other words, the DHCP server will give H1 and H2 random configurations chosen from a fixed range of IP addresses while H3 will receive the same IP address every time it connects to the network.

After creating the Docker image of the server and manually configuring it as needed, you can run the lab. In order to receive the configuration, each node has to ask it directly using the command *dhclient -v eth*, where eth is the interface of the node that needs to be configurated. After that, you can check if it worked with the command *ip addr show* or *ip addr show dev eth* on the configured node. Now you can work with the scenario as you please.


## DHCP2 - more LANs


## DNS server
