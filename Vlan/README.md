# Vlan lab description
The aim of these exercises is to undestand what are VLANs and how to work with them. A **Virtual Local Area Network (VLAN)** is a technology that logically segments a single physical network switch or infrastructure into multiple distinct, isolated networks. It allows devices on different physical ports to act as if they are on the same network, improving security, performance, and management by reducing broadcast domains.

## VlanBase
In this lab, there are four hosts and two switches: H1 and H2 are linked to S1, H3 and H4 are linked to S2 and the two switched are connected together. The purpose of the lab is to create two VLAN over the existent physical network, in particular: H1 and H3 belong to VLAN10 while H2 and H4 belong to VLAN20.
To segment the network, I manually configured each switch interface. Specifically, the interface directly connected to a host is defined with a unique tag (*tag=10*), while the link between the two switches needs to have all the tags explicitly configured to allow packets from each VLAN to pass through (*trunks=10,20*). This configuration is only necessary on the switches.

## VlanExtra
