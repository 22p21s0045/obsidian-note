#recap 

## Symetric key
A symmetric key cipher is a cryptographic system that uses the same secret key for both encryption and decryption processes. This means that the **same key** is used to convert plaintext into ciphertext during encryption and to convert the ciphertext back into plaintext during decryption. Symmetric key ciphers are widely used for their speed and efficiency, as they generally operate faster than asymmetric key ciphers, also known as public-key cryptography

## Asymetric key
Asymmetric key cryptography, also known as public-key cryptography, utilizes a pair of mathematically linked keys: **a public key for encryption and a private key for decryption**. The public key is shared openly, while the private key is kept confidential. Messages encrypted with the public key can only be decrypted by the corresponding private key. This cryptographic system provides secure communication and digital signatures, ensuring data confidentiality and integrity

![](https://i.imgur.com/hxbTwbt.png)


## SNMP
 stands for Simple Network Management Protocol, and it is a protocol used for **managing and monitoring network-connected devices** in Internet Protocol (IP) networks[1](https://www.auvik.com/franklyit/blog/network-basics-what-is-snmp/)[2](https://www.techtarget.com/searchnetworking/definition/SNMP)[3](https://en.wikipedia.org/wiki/Simple_Network_Management_Protocol)[4](https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/)[5](https://www.thousandeyes.com/learning/techtorials/snmp-simple-network-management-protocol). SNMP is used to collect and organize information about managed devices on IP networks, enabling network administrators to monitor and manage network performance, identify devices, track changes, and deliver real-time status updates. SNMP uses a client-server model, with servers called managers and clients called agents.



## SDN (Software-defined networking)
- Have OS to help config
- SDN abstracts the underlying network infrastructure and provides a **centralized controller** that orchestrates network traffic flows and policies

## ACL
![](https://i.imgur.com/jQptnHu.png)



## Openflow
- เป็น software ที่เข้ามาเเทรกอีกทีตามหลักการของ SDN

![](https://i.imgur.com/hQ899oV.png)


## Monitoring
- พยายามหาเหตุ
- Latency (ความหน่วง)
- Traffic
- Errors
- Saturation

## The four golden signals for site availability are:

- **Latency:** This refers to the time it takes for a website to respond to a user request. Low latency means a faster and more responsive user experience.
- **Traffic:** This is the total volume of requests a website receives over a specific period. Monitoring traffic helps identify spikes in demand and potential bottlenecks.
- **Errors:** This refers to the number of requests that fail or result in an error message. A rise in errors can indicate problems with the website's functionality.
- **Saturation (การทํางานสูง):** This refers to the utilization of resources like CPU, memory, and storage on the servers hosting the website. High saturation can lead to slow performance or even outages.

## Black box vs White box monitoring

- **White box monitoring:** Focuses on the internal workings of applications. Examples include <span style="background:#b1ffff">monitoring application logs,</span> database queries, user activity, and response codes.
- **Black box monitoring:** Focuses on the external behavior and health of servers. Examples include monitoring<span style="background:#b1ffff"> CPU usage, memory usage</span>, disk space, and uptime.


[[Physical Layer]]