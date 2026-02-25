# Security lab description

## Man In The Middle
The aim is to demonstrate how network traffic between two communicating nodes can be intercepted and manipulated by malicious external entities. 
In each scenario, a malicious host (which is called **eve** in my lab exercises) was inserted into the network so that it could interfere with communications without the various parties noticing.

Three different attacks are presented:
+ **ARP Spoofing**: The attacker sends fake ARP messages to trick network devices into believing that its MAC address matches the IP address of another device. In other words, the attacker pretends to be another device on the network to receive traffic destined for that device.
+ **Port Stealing**: The attacker sends many Ethernet frames with fake or cloned MAC addresses to confuse the switch and cause traffic to be forwarded to its port as well.

---> <ins>In this particular case</ins>: since the OVS switches in Kathará don't allow to directly see the hash table and the connections to the various ports, I added a command to the lab.conf that allows you to have two separate terminals for eve (*eve[num_terms]=2*): in the first one I execute the attack with ettercap while in the other one I check that the target communication packets pass through the attacker.
+ **DHCP Poisoning**: The attacker pretends to be a DHCP server and assigns false network parameters, such as gateways or DNS, to network devices.

To emulate the attacks, we use the *ettercap* command with its various options available to change the type of attack. But, before executing this command, some changes must be done:
1. First of all, the ettercap command isn't present by default in Kathará, so you need to use a Dockerfile to create a Docker image that installs it. 
2. Next, the forwarding on eve needs to be manually enabled as Docker does not allow you to modify sysctl files at runtime. To do this, the command *eve[sysctl]="net.ipv6.conf.all.forwarding=1* can be written directly in the lab.conf file.
3. At last, the whole network scenario must be restarted with the flag *privileged* activated. This requires to launch the basic Kathará command in this way: *sudo kathara lstart --privileged*. In this way, the user has the root rights to execute the devices in privileged mode in order to make the ettercap command work.


## Firewall



## Cryptography
