#tcp #protocol
# Data package
Basic unit of information that travels form one to another device in network
- Hader : IP address/Mac address /Protocol Number
- Body
- Footer: signature
# Bandwidth
The amount of data device receives every <mark class="hltr-yellow">second</mark>

# Packet Sniffting
- Practice of capturing and inspecting data packets across network

# Transmission Control Protocol
Protocol that allow two device to  form a connection

# IP
Set of standards used for routing and addressing data packets
# Port
- In **computing**, a **port** is a **communication endpoint**.
- It is a **logical address** represented by a **16-bit unsigned integer**.
- Each application on a computer that uses the internet is assigned a port number.
- Ports are used to send or receive data.
		- Port 25 Email
		- Port 443 https
		- port 20 Large file transfer

#layer
# TCP Layer
- Network access layer: creation data packet transmission
- Internet layer: IP address attached to packet
- Transport layer : control flow of traffic
- Application layer

![[Pasted image 20240307084937.png]]
 an internet communication protocol that allows two devices to form a connection and stream data. It ensures that data is reliably transmitted to the destination service. TCP contains the port number of the intended destination service, which resides in the TCP header of a TCP/IP packet.
#UDP #protocol 
# UDP
a connectionless protocol that <mark class="hltr-yellow">does not establish a connection </mark>between devices before transmissions. It is used by applications that are not concerned with the reliability of the transmission. Data sent over UDP is not tracked as extensively as data sent using TCP. Because UDP does not establish network connections, it is used mostly for performance sensitive applications that operate in real time, such as video streaming.
#compare
# TCP/IP model versus OSI model
![[Pasted image 20240307085908.png]]
#ip
# IP address
- IpV4 : decimal point  [[Format of IPv4]]
- IpV6 : 32 character
	public 
	private

#mac-address
# Mac Address
- Switch destination
![](https://i.imgur.com/cAa5Gyq.png)
