3/19/2024
#lecture-3 

[[902_NMS.pdf]] #SNMP

## Simple Network Management Protocol (SNMP)
an Internet Standard protocol used for **collecting and organizing information** about managed devices on IP networks and for modifying that information. SNMP is widely used in network management for monitoring

### Key to manage
- Fault management
- Configuration management
- Accounting management
- Performance management
- Security management

>[!tip]
>The Simple Network Management Protocol is an Internet Standard protocol widely used for a **management station**


### SNMP mechanism 
- SNMP manager—Works on a network management system (NMS) to monitor and manage the SNMP-capable devices in the network. 
- SNMP agent—Works on a managed device to receive and handle requests from the NMS, and send traps to the NMS when some events, such as interface state change, occur. 
- Management Information Base (MIB)—Specifies the variables (for example, interface status and CPU usage) maintained by the SNMP age
![](https://i.imgur.com/zbkJ5ey.png)


![](https://i.imgur.com/j7sG7jA.png)

- Ports: **161 162**


### Management Information Base (MIB) 
a virtual **database** used for managing entities in a communication network, commonly associated with the Simple Network Management Protocol (SNMP). It serves as a critical component of network management, containing

#sflow
## sFlow
is a monitoring technology designed for high-speed switched or routed networks that **collects samples** of network packets and **sends them to a monitoring station** in UDP datagrams. It implements two sampling mechanisms: packet-based sampling, which samples one packet out of a specified number of packets, and time-based sampling, which samples interface statistics at specified intervals. sFlow technology is used for continuous traffic monitoring at wire speed on all interfaces simultaneously,

![](https://i.imgur.com/qVqZl0c.png)

## NTP
  
Synchronizes computer systems' clocks over packet-switched, variable-latency data networks

![](https://i.imgur.com/IkZOUVp.png)
