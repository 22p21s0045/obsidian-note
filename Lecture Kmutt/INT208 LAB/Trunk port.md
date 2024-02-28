- **Trunk ports:** These ports can carry traffic for <mark style="background: #FF5582A6;">**multiple VLANs** simultaneously</mark>. They act as **links between switches**, allowing VLAN traffic to flow across the network.

**1. Increased Bandwidth:**

- A single trunk port can carry traffic for **multiple VLANs**, effectively combining the bandwidth of those VLANs. This is particularly beneficial for **high-bandwidth applications** like video conferencing or data transfer between servers, as it allows for faster transmission across the network.

**2. Improved Scalability:**

- Trunk ports simplify network expansion by providing a **flexible and adaptable** way to connect switches. You can **add new VLANs** without needing additional physical connections, as the existing trunk port can already handle the traffic. This reduces the need for additional cabling and switch ports, which can be expensive and time-consuming to manage.

**3. Enhanced Security:**

- Trunk ports can be used to **segregate different types of traffic** by assigning VLANs based on security needs. This helps to **isolate sensitive information** and restrict unauthorized access within the network. For example, a separate VLAN can be created for guest access, preventing them from accessing sensitive data on other VLANs.

**4. Efficient Network Management:**

- Trunk ports help to **reduce cable clutter** by eliminating the need for numerous individual connections between switches for each VLAN. This simplifies network management and reduces the likelihood of cabling errors or disruptions.

**5. Flexibility in Switch-to-Switch Connections:**

- Trunk ports provide a **single point of connection** between switches, even when they manage different sets of VLANs. This simplifies configuration and reduces the complexity of managing multiple individual connections.
6.** <mark style="background: #FF5582A6;">Packet Tagging</mark>:**

- When a **device connected to a specific VLAN** sends data through a trunk port, the **device itself adds a VLAN tag** to the packet header.
- This tag **identifies the VLAN** the packet belongs to. The format of the tag is typically based on the **IEEE 802.1Q** standard.

ตัวอย่างในการตั้งค่า 
- Port ของ Switch ให้เป็น Trunk Port เช่น 
- Port ที่ทําหน้าที่เชื่อมต่อไปยัง Switch ตัวอื่น ๆ เช่น Uplink Port - Port ที่ทําหน้าที่เชื่อม ไปยัง Routerตัวที่ทําหน้าที่ Route Traffic ระหว่าง VLAN

![[Pasted image 20240228144311.png]]
Imagine a highway with multiple lanes:

- <mark style="background: #FF5582A6;">**Tagged VLAN </mark>= Multi-lane Highway:** The highway can carry traffic for different destinations (VLANS). Each car (network packet) entering the highway is marked with a sign (VLAN tag), indicating its final destination.
- <mark style="background: #FF5582A6;">**Untagged VLAN</mark> = Single-lane Road:** This road is only for traffic going to a specific destination. There's no need for signs (VLAN tags) as all cars on this road are going to the same place.

- A trunk port is configured to handle traffic from **multiple VLANs**.
- It **doesn't belong to a single specific VLAN** like an access port.

