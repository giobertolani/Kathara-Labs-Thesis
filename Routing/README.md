# Routing lab description
In Kathará, devices belonging to the same LAN can communicate directly. They don't know how to reach anything outside that LAN unless an intermediary device is specifically added. In fact, by starting the network scenario and immediately checking the routing table of a device, you can notice that only LANs directly connected to it are automatically included in the table. To solve this problem, you can specify a default route inside the .startup file of the specific device in order to reach all other networks.

In this folder, I uploaded three exercises. the first two execute the same thing, but the structure of the network scenario is quite different, whereas the last one is an official exaple for static routing:
+ **With Switches**: in this lab, there are three hosts (h1, h2, h3) and two OVS switches (s1, s2). H1 belongs to the LAN 192.168.1.0/24, h3 belongs to the LAN 192.168.2.0/24 and h3 belongs to both. Even though two switches are present, the real link between the two networks is h2: this host replaces the role of specific communication devices, which forward packets from one subnet to another. So, it represents the gateway of both networks.
This lab has the same structure and employed logic of the one used for Marionnet during my course in university, but a great part of it is useless or even incorrect. I created and uploaded the correct version of it so that the comparison can be done (the next exercise described).

+ **Without Switches**: in this lab, only the three hosts are present. As before, there are two LANs and h2 belongs to both of them, still working as the gateway.
The lab demonstrates that, in this kind of tests, routers and switches are often not needed. They can be used just to create a more complex network scenario (just like I did in the previous lab).

+ **RomaLab**: the last lab is taken directly from a Kathará's official repository on GitHub. I just recreated the exercise described inside the repo to dive deeper and more consciously into the use of this framework. Here's the link:
https://github.com/KatharaFramework/Kathara-Labs/tree/main/main-labs/basic-topics/static-routing
