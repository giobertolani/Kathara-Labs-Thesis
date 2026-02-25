# Security lab description

## Man In The Middle
The aim is to demonstrate how network traffic between two communicating nodes can be intercepted and manipulated by malicious external entities. 
In each scenario, a malicious host (which is called **eve** in my lab exercises) was inserted into the network so that it could interfere with communications without the various parties noticing. To emulate the attacks, we use the *ettercap* command with its various options available to change the type of attack.

Three different attacks are presented:
+ **ARP Spoofing**: The attacker sends fake ARP messages to trick network devices into believing that its MAC address matches the IP address of another device. In other words, the attacker pretends to be another device on the network to receive traffic destined for that device.
+ **Port Stealing**: The attacker sends many Ethernet frames with fake or cloned MAC addresses to confuse the switch and cause traffic to be forwarded to its port as well.
+ **DHCP Poisoning**: The attacker pretends to be a DHCP server and assigns false network parameters, such as gateways or DNS, to network devices.


## Firewall



## Cryptography
