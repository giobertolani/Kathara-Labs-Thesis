# FirstNet lab description
The network topology was explicitly modeled by defining nodes and connections in a file called **lab.conf**. Unlike Marionnet, in which the network structure is graphically represented, Kathará
requires a textual description that clearly defines the devices and their connections.

For each device, an additional file called **<device_name>.startup** can be created, which specifies the configuration information and actions that can be performed once the network is started.

## basic
Unlike Marionnet, devices belonging to the same LAN do not need to use an intermediate medium to communicate; therefore, a switch or router are not needed. They are only necessary for communications across different LANs.

This folder contains a simple exercise, where just two devices from the same LAN are present. Therefore, they are direcly connected, no other device is needed.

## basic2
The exercise in this folder is still quite simple, it's just a little more articulated that the previous one. In fact, there are still two devices, but now there are three different domains, which have to communicate with each other. 

## router
The last exercise adds a router inside the previous network topology.
