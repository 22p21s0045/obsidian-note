# ## **What Is a VLAN?**

A VLAN, or virtual area network, is a group of devices that share a broadcast domain. On the surface, that doesn’t sound too complicated or special, but the VLAN is a big step up from its predecessor 一 the LAN.

A LAN, or local area network, is a cluster of connected computers housed in a specific area, such as a corporate office. Whenever a broadcast is sent within a LAN, _all_ devices within the network have to process and accept it. 

This puts enormous strain on all of the devices, slows the network down, and makes the data within those broadcasts easily accessible to anyone who can access the network. As a LAN increases in scope, the CPU overhead and lack of security become unsustainable.

That’s why many enterprises have turned to VLANs, which separate a LAN into distinct segments. Typically, organizations create VLANs for every department. Devices within a VLAN can communicate with each other, and each other only. 

Since VLANs are inherently virtual, employees can communicate securely with their peers no matter where they are located. Even if all employees are at the office, VLANs make it easy to add or remove devices from a network without the cabling or infrastructure hassle of a

### Untagged VLANs

Untagged or “access” VLANs are connected to hosts (usually servers) that pass VLAN information to and from each network and cannot differentiate between any VLAN configuration. In this way, untagged VLANs have a more linear structure, moving from A to B rather than from A to B, C, and D. Generally, untagged VLANs are the default.

Here’s how the flow typically goes:

1.<mark style="background: #FFF3A3A6;"> Host A sends traffic to a switch, and the traffic doesn’t have a VLAN tag.
2. Traffic is received on access port 1 (also untagged).</mark>
3. Port 1 adds a VLAN tag to the frame, and the switch dictates that the frame must be sent to Host B through access port 2 (an untagged port).
4. The VLAN tag is removed.
5. Traffic flows to Host B.