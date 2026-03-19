# Security labs description

## Man In The Middle
The aim is to demonstrate how network traffic between two communicating nodes can be intercepted and manipulated by malicious external entities. 
In each scenario, a malicious host (which is called **eve** in my lab exercises) was inserted into the network so that it could interfere with communications without the various parties noticing.

Three different attacks are presented:
+ **ARP Spoofing**: The attacker sends fake ARP messages to trick network devices into believing that its MAC address matches the IP address of another device. In other words, the attacker pretends to be another device on the network to receive traffic destined for that device.
+ **Port Stealing**: The attacker sends many Ethernet frames with fake or cloned MAC addresses to confuse the switch and cause traffic to be forwarded to its port as well.

---> <ins>In this particular case</ins>: since the OVS switches in Kathará don't allow to directly see the hash table and the connections to the various ports, I added a command to the lab.conf that allows you to have two separate terminals for eve (*eve[num_terms]=2*): in the first one I execute the attack with ettercap while in the other one I check that the target communication packets pass through the attacker.
+ **DHCP Poisoning**: The attacker pretends to be a DHCP server and assigns false network parameters, such as gateways or DNS, to network devices. In this lab, eve cannot properly emulate the DNS server, while it seems it works as the DHCP server just fine. 

To emulate the attacks, we use the *ettercap* command with its various options available to change the type of attack. But, before executing this command, some changes must be done:
1. First of all, the ettercap command isn't present by default in Kathará, so you need to use a Dockerfile to create a Docker image that installs it. Then, you must build that image in Kathará before using it.
2. Next, the forwarding on eve needs to be manually enabled as Docker does not allow you to modify sysctl files at runtime. To do this, the command *eve[sysctl]="net.ipv6.conf.all.forwarding=1* can be written directly in the lab.conf file.
3. At last, the whole network scenario must be restarted with the flag *privileged* activated. This requires to launch the basic Kathará command in this way: *sudo kathara lstart --privileged*. In this way, the user has the root rights to execute the devices in privileged mode in order to make the ettercap command work.


## Firewall
This lab consists of setting up *natting* and *firewalling* rules in a network composed of seven devices, where one of them (firewall) acts as a gateway between the three LANs present. The network I created is quite simple, but you can replace each device with other more complex devices like DHCP server, but you need to use the Dockerfile to create the correct Docker image (even for commands like w3m and ftp the image which installs them is required).

The natting and firewall rules can be set in two ways:
+ in a dinamic way: after running the lab, you can write the rules as a command inside the device's tab. In this way, they will be valid as long as the lab is running, the moment you stop it everything will be cancelled;
+ in a static way: you can write the rules directly in the device's startup file so that they will always be active, even when the lab isn't running.


## Cryptography and Certification Authority (CA)
This is a simple lab that can be used to test symmetric and asymmetric encryption, hash functions, Message Authentication Codes (MAC) and ECB Penguin.

A Certification Authority (CA) is an entity that signs digital certificates (web notary). Most current websites reassure their users by using a secure connection for data exchange between client and server (HTTPS protocol). To ensure the authenticity, confidentiality, and integrity of exchanged data, the TLS protocol and digital certificates are used. This lab shows an example of the infrastructure needed to implement a small certificate chain.
