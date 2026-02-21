# Routing lab description
In Kathará, devices belonging to the same LAN can communicate directly. They don't know how to reach anything outside that LAN unless an intermediary device is specifically added. In fact, by starting the network scenario and immediately checking the routing table, you can notice that only LANs directly connected to devices are automatically included in the table. To solve this problem, you can specify a default route in the table: this gateway can be used to reach all other networks.

In this folder, I uploaded two exercises that execute the same thing, but the structure of the network scenario is a bit different:
+ **With Switches**: in this lab, there are three hosts (h1, h2, h3) and two OVS switches (s1, s2). H1 belongs to the LAN 192.168.1.0/24, h3 belongs to the LAN 192.168.2.0/24 and h3 belongs to both. Even though two switches are present, the real link between the two networks is h2: this host replaces the role of specific communication devices, which forward packets from one subnet to another. So, it represents the gateway of both networks.

+ **Without Switches**: in this lab, only the three hosts are present. As before, the two LANs are present and h2 belong to both of them, still working as the gateway.
The lab demonstrates that, in this kind of tests, routers and switch are often not needed. They can be used just to create a more complex network scenario (just like I did in the previous lab).
