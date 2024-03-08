3/7/2024
[[wireless LAN design -2_compressed.pdf]]

Controller wi-fi
![](https://i.imgur.com/Oqa3uw0.png)
#LDAP
## LDAP
1. **LDAP (Lightweight Directory Access Protocol)**:
    
    - **Protocol**: LDAP is an open, cross-platform standard for querying and modifying directory services.
    - **Function**: It allows applications to access and manage distributed directory information services over an IP network.
    - **Usage**: LDAP is used to communicate with various types of directories, including Active Directory.
    - **Authentication**: It handles authentication and enables tasks like email lookups and printer connections.
    - **Vendor-Neutral**: LDAP is not tied to any specific vendor and can work with different directory services.
### Link

```js
https://students.sit.kmutt.ac.th/ldap207admin/htdocs
```
```
Username:  uid=lab207,ou=People,ou=staff,dc=sit,dc=kmutt,dc=ac,dc=th

Password:  Lab!!207
```

## Generate Key NTLM password
```
9997A8DA117B46148EA4E69AF589575A
```


![](https://i.imgur.com/wamIXx4.png)

- Active directory เก็บ **account**

# AAA authentication authorization accounting
- Accounting เก็บว่าทําอะไรไปบ้าง
#protocol 
## Radius Protocol
![](https://i.imgur.com/MELwBve.png)

|**Aspect**|**LDAP (Lightweight Directory Access Protocol)**|**RADIUS (Remote Authentication Dial-In User Service)**|
|---|---|---|
|**Purpose**|Used for managing and accessing directories.|Provides centralized authentication, authorization, and accounting for remote access scenarios.|
|**Authentication**|Handles user authentication and directory searches.|Authenticates users connecting to network access servers (e.g., VPNs, routers, switches).|
|**Protocol Type**|Open-source protocol with a flexible architecture.|Network protocol with centralized services (authentication, accounting, authorization).|
|**Security**|Provides less security compared to RADIUS. Default LDAP communication is not encrypted.|Offers higher security. Supports encryption and strong authentication capabilities.|
|**Scalability**|Not as scalable as RADIUS, especially in high-traffic environments.|Scalable, suitable for large-scale deployments.|
|**Complexity**|Can be complex to configure and manage, especially for large-scale deployments.|Simpler to set up and manage.|
|**Integration**|Can be integrated with other authentication protocols (e.g., Kerberos, SAML).|Used to authenticate various devices (wireless access points, VPNs, firewalls).|
|**Centralized Management**|Provides centralized management for user authentication across multiple servers and services.|Centralized authentication and authorization, making user access management easier.|
|**Use Cases**|Commonly used for user authentication, directory searches, and user management.|Ideal for protecting sensitive information in remote access scenarios (e.g., VPNs).|
|**Example Scenario**|Managing user accounts and organizational data within an enterprise.|Authenticating users connecting to a corporate VPN or wireless network.|6
#ieee

802.1x For <mark class="hltr-yellow">authentication</mark>
![](https://i.imgur.com/qH0AZZP.png)

```
  
*********************************************************************************************************
 3/7/2024 15:31:11 PM    Target: MasterAP (VC)    Command: show ap debug auth-trace-buf 
*********************************************************************************************************
Auth Trace Buffer
-----------------
                                                                                                      
                                                                                                      
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  5   218    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  5   -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            6   220    
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            6   136    
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  6   348    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  6   -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            7   57     
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            7   6      
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  7   218    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  7   -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            8   40     
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            8   45     
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  8   257    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  8   -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            9   74     
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            9   99     
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  9   311    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  9   -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            10  82     
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            10  37     
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  10  249    10.13.104.34
Mar  7 15:27:42  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  10  -      
Mar  7 15:27:42  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  46     
Mar  7 15:27:42  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  46     
Mar  7 15:27:42  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  11  258    10.13.104.34
Mar  7 15:27:42  rad-accept            <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  11  -      
Mar  7 15:27:42  eap-success           <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  4      
Mar  7 15:27:42  wpa3-key1-vm          <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   95     
Mar  7 15:27:42  wpa3-key2-vm          ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   31488  
Mar  7 15:27:42  wpa3-key3-vm          <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   191    
Mar  7 15:27:42  wpa3-key4-vm          ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   24320  
Mar  7 15:28:47  station-up             *  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   -      wpa3 aes-ccmp-128
Mar  7 15:28:47  eap-id-req            <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            1   5      
Mar  7 15:28:47  eap-id-resp           ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            1   14     048Pasito
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            12  208    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  12  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            2   6      
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            2   261    
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  13  475    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  13  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            3   1004   
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            3   6      
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  14  218    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  14  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            4   1000   
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            4   6      
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  15  218    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  15  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            5   1000   
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            5   6      

Auth Trace Buffer
-----------------
                                                                                                      
                                                                                                      
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  16  218    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  16  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            6   220    
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            6   136    
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  17  348    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  17  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            7   57     
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            7   6      
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  18  218    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  18  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            8   40     
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            8   45     
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  19  257    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  19  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            9   74     
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            9   99     
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  20  311    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  20  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            10  82     
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            10  37     
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  21  249    10.13.104.34
Mar  7 15:28:47  rad-resp              <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  21  -      
Mar  7 15:28:47  eap-req               <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  46     
Mar  7 15:28:47  eap-resp              ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  46     
Mar  7 15:28:47  rad-req               ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  22  258    10.13.104.34
Mar  7 15:28:47  rad-accept            <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12/11 RADIUS  22  -      
Mar  7 15:28:47  eap-success           <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            11  4      
Mar  7 15:28:47  wpa3-key1-vm          <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   95     
Mar  7 15:28:47  wpa3-key2-vm          ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   35584  
Mar  7 15:28:47  wpa3-key3-vm          <-  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   191    
Mar  7 15:28:47  wpa3-key4-vm          ->  70:d8:23:00:e9:e3  b8:3a:5a:8b:28:12            -   24320  
Mar  7 15:29:44  station-up             *  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            -   -      wpa3 aes-ccmp-128
Mar  7 15:29:44  eap-id-req            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            1   5      
Mar  7 15:29:44  eap-start             ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            -   -      
Mar  7 15:29:44  eap-id-req            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            1   5      
Mar  7 15:29:49  eap-id-req            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            1   5      
Mar  7 15:29:54  eap-id-req            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            2   5      
Mar  7 15:29:59  eap-id-req            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            2   5      
Mar  7 15:30:00  eap-id-resp           ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            2   17     098trashtalk
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            23  212    10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  23  -      
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            3   6      
Mar  7 15:30:00  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            3   261    
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  24  476    10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  24  -      
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            4   1004   
Mar  7 15:30:00  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            4   6      
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  25  219    10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  25  -      
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            5   1000   

Auth Trace Buffer
-----------------
                                                                                                     
                                                                                                     
Mar  7 15:30:00  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            5   6     
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  26  219   10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  26  -     
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            6   1000  
Mar  7 15:30:00  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            6   6     
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  27  219   10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  27  -     
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            7   220   
Mar  7 15:30:00  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            7   136   
Mar  7 15:30:00  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  28  349   10.13.104.34
Mar  7 15:30:00  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  28  -     
Mar  7 15:30:00  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            8   57    
Mar  7 15:30:01  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            8   6     
Mar  7 15:30:01  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  29  219   10.13.104.34
Mar  7 15:30:01  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  29  -     
Mar  7 15:30:01  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            9   40    
Mar  7 15:30:01  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            9   48    
Mar  7 15:30:01  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  30  261   10.13.104.34
Mar  7 15:30:01  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  30  -     
Mar  7 15:30:01  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            10  74    
Mar  7 15:30:01  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            10  102   
Mar  7 15:30:01  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  31  315   10.13.104.34
Mar  7 15:30:01  rad-resp              <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  31  -     
Mar  7 15:30:01  eap-req               <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            11  46    
Mar  7 15:30:01  eap-resp              ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            11  46    
Mar  7 15:30:01  rad-req               ->  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  32  259   10.13.104.34
Mar  7 15:30:01  rad-reject            <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12/11 RADIUS  32  -     
Mar  7 15:30:02  eap-failure           <-  70:d8:23:00:f2:bc  b8:3a:5a:8b:28:12            11  4     server rejected


*********************************************************************************************************
 3/7/2024 15:30:38 PM    Target: MasterAP (VC)    Command: show ale status 
*********************************************************************************************************
ALE Status
----------
Type                            Value
----                            -----
ale login status                False
ale login status code           
ale fail times                  0
ale request state               Idle
ale rssi post request buffered  0
ale free to send count          4
ale send buffer ageout count    0


*********************************************************************************************************
 3/7/2024 15:30:25 PM    Target: MasterAP (VC)    Command: show tech-support memory 
*********************************************************************************************************
Memory Summary:
MemTotal:        1028792 kB
MemFree:          520308 kB
MemAvailable:     606168 kB
Buffers:               0 kB
Cached:            94232 kB
SwapCached:            0 kB
Active:           126396 kB
Inactive:          75088 kB
Active(anon):     107256 kB
Inactive(anon):        0 kB
Active(file):      19140 kB
Inactive(file):    75088 kB
Unevictable:           0 kB
Mlocked:               0 kB
HighTotal:        270332 kB
HighFree:         201572 kB
LowTotal:         758460 kB
LowFree:          318736 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:        107080 kB
Mapped:            52172 kB
Shmem:                 0 kB
Slab:             234352 kB
SReclaimable:       3212 kB
SUnreclaim:       231140 kB
KernelStack:         952 kB
PageTables:         1492 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:      514396 kB
Committed_AS:     163952 kB
VmallocTotal:     245760 kB
VmallocUsed:       76952 kB
VmallocChunk:      95900 kB

Slabinfo:
slabinfo - version: 2.1
# name                 : tunables    : slabdata   
bcmVlan_blogRule_id      0      0     16  240    1 : tunables  120   60    8 : slabdata      0      0      0
bcmVlan_flowPath       0      0     16  240    1 : tunables  120   60    8 : slabdata      0      0      0
bcmVlan_flowDev        0      0     16  240    1 : tunables  120   60    8 : slabdata      0      0      0
bcmvlan_tableEntry      0      0    448    9    1 : tunables   54   27    8 : slabdata      0      0      0
bcmvlan_realDev        0      0    464    8    1 : tunables   54   27    8 : slabdata      0      0      0
bcmvlan_vlanDev        0      0     24  163    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_mld_exception_cache      0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_mld_rep_cache      0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_mld_grp_cache      0      0    128   31    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_igmp_exception_cache      0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_igmp_rep_cache      0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
bcm_mcast_igmp_grp_cache      0      0    128   31    1 : tunables  120   60    8 : slabdata      0      0      0
cmdlist_buffer         0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
ubi_wl_entry_slab    996   1141     24  163    1 : tunables  120   60    8 : slabdata      7      7      0
ubifs_inode_slab      24     45    416    9    1 : tunables   54   27    8 : slabdata      5      5      0
SCTPv6                 1      7   1152    7    2 : tunables   24   12    8 : slabdata      1      1      0
SCTP                   0      0   1024    4    1 : tunables   54   27    8 : slabdata      0      0      0
sctp_chunk             0      0    192   21    1 : tunables  120   60    8 : slabdata      0      0      0
sctp_bind_bucket       0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
tw_sock_DCCPv6         0      0    168   24    1 : tunables  120   60    8 : slabdata      0      0      0
request_sock_DCCPv6      0      0    264   15    1 : tunables   54   27    8 : slabdata      0      0      0
DCCPv6                 1      5   1472    5    2 : tunables   24   12    8 : slabdata      1      1      0
tw_sock_DCCP           0      0    168   24    1 : tunables  120   60    8 : slabdata      0      0      0
request_sock_DCCP      0      0    264   15    1 : tunables   54   27    8 : slabdata      0      0      0
DCCP                   1      3   1344    3    1 : tunables   24   12    8 : slabdata      1      1      0
ccid3_hc_tx_sock       0      0    192   21    1 : tunables  120   60    8 : slabdata      0      0      0
ccid3_hc_rx_sock       0      0    128   31    1 : tunables  120   60    8 : slabdata      0      0      0
ccid2_hc_tx_sock       0      0    704   11    2 : tunables   54   27    8 : slabdata      0      0      0
ccid2_hc_rx_sock       0      0     16  240    1 : tunables  120   60    8 : slabdata      0      0      0
tfrc_rxh_cache         0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
tfrc_tx_hist           0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
tfrc_li_hist           0      0     16  240    1 : tunables  120   60    8 : slabdata      0      0      0
dccp_ackvec_record      0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
dccp_ackvec            0      0    576    7    1 : tunables   54   27    8 : slabdata      0      0      0
dccp_bind_bucket       0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
bridge_fdb_cache       0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
xfrm6_tunnel_spi       0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
ip6-frags              0      0    168   24    1 : tunables  120   60    8 : slabdata      0      0      0
fib6_nodes            24    124     32  124    1 : tunables  120   60    8 : slabdata      1      1      0
ip6_dst_cache         19     48    256   16    1 : tunables  120   60    8 : slabdata      3      3      0
ip6_mrt_cache          0      0    128   31    1 : tunables  120   60    8 : slabdata      0      0      0
PINGv6                 0      0    832    9    2 : tunables   54   27    8 : slabdata      0      0      0
RAWv6                  8      9    832    9    2 : tunables   54   27    8 : slabdata      1      1      0
UDPLITEv6              0      0    832    9    2 : tunables   54   27    8 : slabdata      0      0      0
UDPv6                 23     27    832    9    2 : tunables   54   27    8 : slabdata      3      3      0
tw_sock_TCPv6        134    240    200   20    1 : tunables  120   60    8 : slabdata     12     12      0
request_sock_TCPv6      0      0    240   17    1 : tunables  120   60    8 : slabdata      0      0      0
TCPv6                  9     12   1664    4    2 : tunables   24   12    8 : slabdata      3      3      0
bpmbuf                 0      0   4736    1    2 : tunables    8    4    0 : slabdata      0      0      0
mqueue_inode_cache      1      8    512    8    1 : tunables   54   27    8 : slabdata      1      1      0
ntfs_big_inode_cache      0      0    512    8    1 : tunables   54   27    8 : slabdata      0      0      0
ntfs_inode_cache       0      0    200   20    1 : tunables  120   60    8 : slabdata      0      0      0
ntfs_name_cache        0      0    512    8    1 : tunables   54   27    8 : slabdata      0      0      0
ntfs_attr_ctx_cache      0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
ntfs_index_ctx_cache      0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
fat_inode_cache        0      0    408   10    1 : tunables   54   27    8 : slabdata      0      0      0
fat_cache              0      0     24  163    1 : tunables  120   60    8 : slabdata      0      0      0
dio                    0      0    384   10    1 : tunables   54   27    8 : slabdata      0      0      0
fasync_cache           0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
posix_timers_cache      0      0    176   23    1 : tunables  120   60    8 : slabdata      0      0      0
UNIX                 231    242    704   11    2 : tunables   54   27    8 : slabdata     22     22      0
ip4-frags              1     28    144   28    1 : tunables  120   60    8 : slabdata      1      1      0
UDP-Lite               0      0    704   11    2 : tunables   54   27    8 : slabdata      0      0      0
tcp_bind_bucket        5    124     32  124    1 : tunables  120   60    8 : slabdata      1      1      0
inet_peer_cache       54     96    128   32    1 : tunables  120   60    8 : slabdata      3      3      0
secpath_cache          0      0     32  124    1 : tunables  120   60    8 : slabdata      0      0      0
flow_cache             0      0     88   46    1 : tunables  120   60    8 : slabdata      0      0      0
xfrm_dst_cache         0      0    320   12    1 : tunables   54   27    8 : slabdata      0      0      0
ip_fib_trie           12    124     32  124    1 : tunables  120   60    8 : slabdata      1      1      0
ip_fib_alias          16    124     32  124    1 : tunables  120   60    8 : slabdata      1      1      0
ip_dst_cache          24     93    128   31    1 : tunables  120   60    8 : slabdata      3      3      0
PING                   0      0    640    6    1 : tunables   54   27    8 : slabdata      0      0      0
RAW                    8     11    704   11    2 : tunables   54   27    8 : slabdata      1      1      0
UDP                  102    143    704   11    2 : tunables   54   27    8 : slabdata     13     13      0
tw_sock_TCP            0      0    200   20    1 : tunables  120   60    8 : slabdata      0      0      0
request_sock_TCP       3     17    240   17    1 : tunables  120   60    8 : slabdata      1      1      0
TCP                    5     15   1536    5    2 : tunables   24   12    8 : slabdata      3      3      0
eventpoll_pwq         51    198     40   99    1 : tunables  120   60    8 : slabdata      2      2      0
eventpoll_epi         52    124    128   31    1 : tunables  120   60    8 : slabdata      4      4      0
blog_rule              0      0    256   16    1 : tunables  120   60    8 : slabdata      0      0      0
sgpool-128             2      2   2048    2    1 : tunables   24   12    8 : slabdata      1      1      0
sgpool-64              2      4   1024    4    1 : tunables   54   27    8 : slabdata      1      1      0
sgpool-32              2      8    512    8    1 : tunables   54   27    8 : slabdata      1      1      0
sgpool-16              2     16    256   16    1 : tunables  120   60    8 : slabdata      1      1      0
sgpool-8               2     32    128   32    1 : tunables  120   60    8 : slabdata      1      1      0
scsi_data_buffer       0      0     24  163    1 : tunables  120   60    8 : slabdata      0      0      0
blkdev_queue           4      7   1128    7    2 : tunables   24   12    8 : slabdata      1      1      0
blkdev_requests       16     19    208   19    1 : tunables  120   60    8 : slabdata      1      1      0
blkdev_ioc             0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
bio-0                  2     32    128   32    1 : tunables  120   60    8 : slabdata      1      1      0
biovec-256             2      2   3072    2    2 : tunables   24   12    8 : slabdata      1      1      0
biovec-128             0      0   1536    5    2 : tunables   24   12    8 : slabdata      0      0      0
biovec-64              0      0    768    5    1 : tunables   54   27    8 : slabdata      0      0      0
biovec-16              0      0    192   21    1 : tunables  120   60    8 : slabdata      0      0      0
uid_cache              0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
sock_inode_cache     323    390    384   10    1 : tunables   54   27    8 : slabdata     39     39      0
skbuff_fclone_cache     50     77   1088    7    2 : tunables   24   12    8 : slabdata     11     11      0
skbuff_head_cache  34562  34928    512    8    1 : tunables   54   27    8 : slabdata   4366   4366    135
file_lock_cache      113    192    128   32    1 : tunables  120   60    8 : slabdata      6      6      0
file_lock_ctx         22    124     32  124    1 : tunables  120   60    8 : slabdata      1      1      0
shmem_inode_cache      1     11    352   11    1 : tunables   54   27    8 : slabdata      1      1      0
pool_workqueue         8     32    256   16    1 : tunables  120   60    8 : slabdata      2      2      0
proc_inode_cache    3043   3179    344   11    1 : tunables   54   27    8 : slabdata    289    289     20
sigqueue             108    140    144   28    1 : tunables  120   60    8 : slabdata      5      5      0
bdev_cache             1      8    512    8    1 : tunables   54   27    8 : slabdata      1      1      0
kernfs_node_cache   6813   6850     80   50    1 : tunables  120   60    8 : slabdata    137    137      0
mnt_cache             19     42    192   21    1 : tunables  120   60    8 : slabdata      2      2      0
filp                1710   2247    192   21    1 : tunables  120   60    8 : slabdata    107    107    300
inode_cache         2484   2535    312   13    1 : tunables   54   27    8 : slabdata    195    195      0
dentry              6330   6330    136   30    1 : tunables  120   60    8 : slabdata    211    211    120
names_cache           51     51   4096    1    1 : tunables   24   12    8 : slabdata     51     51      0
buffer_head            0      0     64   63    1 : tunables  120   60    8 : slabdata      0      0      0
nsproxy                1    163     24  163    1 : tunables  120   60    8 : slabdata      1      1      0
vm_area_struct      3518   4922     88   46    1 : tunables  120   60    8 : slabdata    107    107    240
mm_struct            160    180    448    9    1 : tunables   54   27    8 : slabdata     20     20      0
fs_cache             167    315     64   63    1 : tunables  120   60    8 : slabdata      5      5      0
files_cache          222    272    256   16    1 : tunables  120   60    8 : slabdata     17     17      0
signal_cache         178    224    576    7    1 : tunables   54   27    8 : slabdata     32     32      0
sighand_cache        154    165   1344    3    1 : tunables   24   12    8 : slabdata     55     55      0
task_struct          154    195   1472    5    2 : tunables   24   12    8 : slabdata     38     39      0
cred_jar             417    558    128   31    1 : tunables  120   60    8 : slabdata     18     18      0
anon_vma_chain      2376   4216     32  124    1 : tunables  120   60    8 : slabdata     34     34    240
anon_vma            1858   2407     48   83    1 : tunables  120   60    8 : slabdata     29     29    300
pid                  186    378     64   63    1 : tunables  120   60    8 : slabdata      6      6      0
radix_tree_node      784    819    304   13    1 : tunables   54   27    8 : slabdata     63     63      0
idr_layer_cache      141    154   1072    7    2 : tunables   24   12    8 : slabdata     22     22      0
kmalloc-4194304        0      0 4194304    1 1024 : tunables    1    1    0 : slabdata      0      0      0
kmalloc-2097152        0      0 2097152    1  512 : tunables    1    1    0 : slabdata      0      0      0
kmalloc-1048576        8      8 1048576    1  256 : tunables    1    1    0 : slabdata      8      8      0
kmalloc-524288         5      5 524288    1  128 : tunables    1    1    0 : slabdata      5      5      0
kmalloc-262144         8      8 262144    1   64 : tunables    1    1    0 : slabdata      8      8      0
kmalloc-131072         6      6 131072    1   32 : tunables    8    4    0 : slabdata      6      6      0
kmalloc-65536       2626   2626  65536    1   16 : tunables    8    4    0 : slabdata   2626   2626      0
kmalloc-32768        161    161  32768    1    8 : tunables    8    4    0 : slabdata    161    161      0
kmalloc-16384        104    116  16384    1    4 : tunables    8    4    0 : slabdata    104    116      0
kmalloc-8192        1977   1987   8192    1    2 : tunables    8    4    0 : slabdata   1977   1987      0
kmalloc-4096         114    114   4096    1    1 : tunables   24   12    8 : slabdata    114    114      0
kmalloc-2048         436    460   2048    2    1 : tunables   24   12    8 : slabdata    230    230     84
kmalloc-1024         593    604   1024    4    1 : tunables   54   27    8 : slabdata    151    151     54
kmalloc-512         1016   1016    512    8    1 : tunables   54   27    8 : slabdata    127    127    135
kmalloc-256          694    736    256   16    1 : tunables  120   60    8 : slabdata     46     46      0
kmalloc-192          466    546    192   21    1 : tunables  120   60    8 : slabdata     26     26      0
kmalloc-128        10856  10880    128   32    1 : tunables  120   60    8 : slabdata    340    340      0
kmalloc-64         19875  19908     64   63    1 : tunables  120   60    8 : slabdata    316    316      0
kmem_cache           144    186    128   31    1 : tunables  120   60    8 : slabdata      6      6      0

Rootfs:
0	/usr/bin
0	/usr/lib
0	/usr/share/dhcpc
0	/usr/share/udhcpc
0	/usr/share
1	/usr/sbin
2	/usr
0	/mnt
0	/dev/shm
0	/dev/net
0	/dev
0	/aruba/ap1x
0	/aruba/cacertrehash
1	/aruba/conf/CA
0	/aruba/conf/CUST_CA
0	/aruba/conf/pki/aruba_ca
0	/aruba/conf/pki/aruba_low_assurance_ca
0	/aruba/conf/pki
1	/aruba/conf
33	/aruba/bin
0	/aruba/lib
0	/aruba/certs
1	/aruba/reg_table
0	/aruba/upgrade
0	/aruba/radius/freeradius
0	/aruba/radius/raddb-term/modules
0	/aruba/radius/raddb-term/sites-available
0	/aruba/radius/raddb-term/sites-enabled
0	/aruba/radius/raddb-term
0	/aruba/radius/raddb/modules
0	/aruba/radius/raddb/sites-available
0	/aruba/radius/raddb/sites-enabled
0	/aruba/radius/raddb
0	/aruba/radius/certs
0	/aruba/radius
35	/aruba
0	/etc/httpd/hotspot/icons
0	/etc/httpd/hotspot
0	/etc/httpd/custom/text
0	/etc/httpd/custom/image
0	/etc/httpd/custom
6	/etc/httpd/core/previous_core
6	/etc/httpd/core
0	/etc/httpd/jscripts/third_party
1	/etc/httpd/jscripts
0	/etc/httpd/images/skin/aruba
0	/etc/httpd/images/skin
0	/etc/httpd/images
0	/etc/httpd/skins/aruba/i18n
0	/etc/httpd/skins/aruba
0	/etc/httpd/skins
0	/etc/httpd/fonts
0	/etc/httpd/styles/aruba
0	/etc/httpd/styles
1	/etc/httpd/i18n/help
1	/etc/httpd/i18n/localization
1	/etc/httpd/i18n
9	/etc/httpd
0	/etc/init.d
1	/etc/ppp/peers
1	/etc/ppp
0	/etc/ssh
11	/etc
1	/bin
1	/lib/modules
0	/lib/firmware
10	/lib
0	/tmp/ssid/3133204b414b
0	/tmp/ssid/3233
0	/tmp/ssid/3132
0	/tmp/ssid/3133
0	/tmp/ssid/3231
0	/tmp/ssid/3232
0	/tmp/ssid/3135
0	/tmp/ssid/3131
0	/tmp/ssid/3030
0	/tmp/ssid/3235
0	/tmp/ssid/5f5f77697265645f5f65746831
0	/tmp/ssid
0	/tmp/role/3233
0	/tmp/role/3132
0	/tmp/role/3133
0	/tmp/role/3231
0	/tmp/role/3232
0	/tmp/role/31346b7579526169535553
0	/tmp/role/3135
0	/tmp/role/3131
0	/tmp/role/3030
0	/tmp/role/3235
0	/tmp/role/64646f6c2061726d79
0	/tmp/role/77697265642d5365744d655570
0	/tmp/role/64656661756c745f77697265645f706f72745f70726f66696c65
0	/tmp/role
0	/tmp/web_security
0	/tmp/tempCertKey
0	/tmp/deviceCerts
0	/tmp/blefwdl
0	/tmp/tempEST/decrypted
0	/tmp/tempEST
0	/tmp/core
0	/tmp/nameservers
0	/tmp/nexthops
0	/tmp/ap1x_cert
0	/tmp/cert/app_cert
0	/tmp/cert/public/psk
0	/tmp/cert/public
0	/tmp/cert/server/psk
0	/tmp/cert/server
0	/tmp/cert/trustedca
0	/tmp/cert/client/psk
0	/tmp/cert/client
0	/tmp/cert
0	/tmp/.papi
0	/tmp/.sock
0	/tmp/apfc
0	/tmp/spectrum
0	/tmp/prov_logs
24	/tmp
0	/var/run/mini_httpd
0	/var/run/rdnssd
0	/var/run/iperf3
0	/var/run/tinyproxy
0	/var/run
0	/var/tmp
0	/var/www
0	/var/log/trace
0	/var/log/iperf3
0	/var/log/arubalog
0	/var/log/tinyproxy
0	/var/log
0	/var/udmd/plugins/lua
0	/var/udmd/plugins
0	/var/udmd
0	/var
0	/debug
0	/sbin
85	

Temp Directory:
-rw-------    1 root     root     23849788 Mar  7 13:02 apcli
-rw-r--r--    1 root     root       107236 Jan  1  1970 option.ko
-rw-r--r--    1 root     root        82268 Jan  1  1970 ftdi_sio.ko
-rw-r--r--    1 root     root        65592 Mar  7 15:15 ble_debug_log.1
-rw-------    1 root     root        65536 Mar  7 14:08 ecp_shared
-rw-r--r--    1 root     root        62748 Jan  1  1970 newGobiNet.ko
-rw-r--r--    1 root     root        53570 Mar  7 15:30 ble_debug_log
-rw-r--r--    1 root     root        44592 Jan  1  1970 usbserial.ko
-rw-r--r--    1 root     root        40468 Jan  1  1970 usbnet.ko
-rw-r--r--    1 root     root        34724 Jan  1  1970 cdc-acm.ko
-rw-r--r--    1 root     root        27500 Jan  1  1970 cp210x.ko
-rw-r--r--    1 root     root        19672 Jan  1  1970 pl2303.ko
-rw-------    1 root     root        19554 Mar  7 15:30 .cli_msg_bG5SHr
-rw-------    1 root     root        16808 Mar  7 13:05 flashophist
-rw-r--r--    1 root     root        16474 Mar  7 15:24 sapd_debug_log.2
-rw-r--r--    1 root     root        16434 Mar  7 13:04 sapd_debug_log.3
-rw-r--r--    1 root     root        16418 Mar  7 13:03 sapd_debug_log.5
-rw-r--r--    1 root     root        16396 Mar  7 15:24 sapd_debug_log.1
-rw-r--r--    1 root     root        16388 Mar  7 13:03 sapd_debug_log.4
-rw-r--r--    1 root     root        14746 Mar  7 15:29 tunnel_debug.log
-rw-------    1 root     root        12288 Mar  7 15:30 sid_shared
-rw-r--r--    1 root     root        10908 Jan  1  1970 usb_wwan.ko
-rw-r--r--    1 root     root         9273 Mar  7 15:28 sapd_debug_log
-rw-r--r--    1 root     root         9249 Mar  7 15:30 ble_relay_log
-rw-r--r--    1 root     root         8756 Mar  7 15:28 cfg-encrypted
-rw-------    1 root     root         8497 Mar  7 15:28 startup-config
-rw-r--r--    1 root     root         8496 Mar  7 15:28 cfg-plaintext
-rw-r--r--    1 root     root         8495 Jan  1  1970 fat_ap_cfg
-rw-r--r--    1 root     root         8495 Jan  1  1970 usb_param_from_cfg
-rw-------    1 root     root         8192 Mar  7 15:30 ssid_info_shared
-rw-r--r--    1 root     root         8127 Mar  7 13:02 bootuplog
-rw-r--r--    1 root     root         7748 Mar  7 15:30 msgh_debug_counters
-rw-r--r--    1 root     root         7510 Mar  7 13:02 aruba_rand
-rw-r--r--    1 root     root         6958 Mar  7 15:27 deviceCertLib.log.debug
-rw-r--r--    1 root     root         6368 Jan  1  1970 cdc_eem.ko
-rw-r--r--    1 root     root         5881 Mar  7 15:27 activate_debug_cert_chain.pem
-rw-r--r--    1 root     root         4446 Mar  7 15:27 deviceCertLib_2.log.debug
-rw-r--r--    1 root     root         4277 Mar  7 15:30 dump_radius_attributes
-rw-------    1 root     root         4080 Mar  7 13:03 dtshm
-rw-r--r--    1 root     root         3120 Mar  7 15:29 lldp.log
-rw-r--r--    1 root     root         3084 Mar  7 13:02 apwl
-rw-r--r--    1 root     root         2756 Mar  7 15:30 script_temp_output
-rw-r--r--    1 root     root         2543 Jan  1  1970 dhcp6.log
-rw-r--r--    1 root     root         2249 Mar  7 15:03 ntpd.log
-rw-r--r--    1 root     root         2048 Mar  7 13:03 default_dhcpopt82_1.xml
-rw-r--r--    1 root     root         2048 Mar  7 13:03 default_dhcpopt82_2.xml
-rw-r--r--    1 root     root         1971 Mar  7 13:03 bd_bootlog
-rw-r--r--    1 root     root         1760 Mar  7 15:29 central_debug_cert_chain.pem
-rw-r--r--    1 root     root         1561 Mar  7 13:03 eirp_info_5g.log
-rw-r--r--    1 root     root         1434 Jan  1  1970 dad
-rw-------    1 root     root         1280 Mar  7 14:08 ecp_proxy_shared
-rw-r--r--    1 root     root         1205 Mar  7 13:03 routing_debug.log
-rw-r--r--    1 root     root         1091 Mar  7 15:30 dnsmasq.leases
-rw-r--r--    1 root     root          807 Mar  7 13:03 ntpdate.log1
-rw-r--r--    1 root     root          746 Jan  1  1970 usb_mod_cleanup
-rw-r--r--    1 root     root          512 Mar  7 13:03 ntpdate_rst.log
-rw-r--r--    1 root     root          461 Jan  1  1970 ap-info
-rw-r--r--    1 root     root          316 Jan  1  1970 dhcp.log
-rw-r--r--    1 root     root          313 Jan  1  1970 mod_load_fail
-rw-r--r--    1 root     root          284 Jan  1  1970 image_info
-rw-r--r--    1 root     root          273 Mar  7 13:03 debug_dhcprelay
-rw-r--r--    1 root     root          238 Mar  7 15:30 mem_cpu_util
-rw-r--r--    1 root     root          223 Mar  7 15:30 gas_req_table
-rw-r--r--    1 root     root          216 Mar  7 15:22 swarm-ip
-rw-r--r--    1 root     root          204 Mar  7 13:02 lldp_gvrp_sock
-rw-r--r--    1 root     root          187 Mar  7 15:22 swarm-serial-number
-rw-r--r--    1 root     root          177 Mar  7 13:02 ntpdate.log
-rw-r--r--    1 root     root          145 Mar  7 13:02 usb.map
-rw-r--r--    1 root     root          130 Mar  7 13:03 nr-per-ap-settings-plaintext-current
-rw-r--r--    1 root     root          109 Jan  1  1970 fcctl.tmp
-rw-r--r--    1 root     root          102 Mar  7 13:03 primary_tunnel_debug.log
-rw-r--r--    1 root     root          101 Mar  7 13:03 bkup_tunnel_debug.log
-rw-r--r--    1 root     root           96 Jan  1  1970 fl_cfg
-rw-r--r--    1 root     root           76 Mar  7 13:02 am1.logs
-rw-r--r--    1 root     root           68 Mar  7 13:03 nl_debug_log
-rw-r--r--    1 root     root           56 Mar  7 13:03 ble_and_zigbee_info.log
-rw-r--r--    1 root     root           50 Mar  7 13:02 aruba_md5
-rw-r--r--    1 root     root           34 Jan  1  1970 aruba_version
-rw-r--r--    1 root     root           34 Mar  7 15:30 cpu_peak_util
-rw-r--r--    1 root     root           31 Jan  1  1970 br0_ipv6_address
-rw-r--r--    1 root     root           31 Mar  7 13:02 reboot_reason
-rw-r--r--    1 root     root           24 Mar  7 13:03 dhcprelay.conf
-rw-r--r--    1 root     root           23 Mar  7 15:02 ap_domains
-rw-r--r--    1 root     root           18 Jan  1  1970 eth0_mac
-rw-r--r--    1 root     root           18 Jan  1  1970 oem_domainname
-rw-------    1 root     root           16 Mar  7 14:08 cli_oos_shared
-rw-r--r--    1 root     root           16 Mar  7 13:03 tpmKeyHandles.bin
-rw-r--r--    1 root     root           14 Mar  7 15:02 dhcp_nexthop
-rw-r--r--    1 root     root           14 Mar  7 15:28 nr-cfg-plaintext-current
-rw-r--r--    1 root     root           13 Mar  7 15:02 dhcp_gotip
-rw-r--r--    1 root     root           13 Mar  7 13:03 virtual_controller_ip
-rw-r--r--    1 root     root           12 Mar  7 13:03 .web_server_cfg
-rw-r--r--    1 root     root           12 Mar  7 13:03 apip
-rw-r--r--    1 root     root           12 Jan  1  1970 servername
-rw-------    1 root     root           11 Jan  1  1970 dhcp_ntp_cfg
-rw-r--r--    1 root     root           11 Mar  7 13:03 serial
-rw-r--r--    1 root     root            9 Jan  1  1970 boardname
-rw-r--r--    1 root     root            9 Jan  1  1970 cpu_assembly_num
-rw-r--r--    1 root     root            9 Mar  7 13:03 gwaddr
-rw-r--r--    1 root     root            9 Jan  1  1970 ntp_server
-rw-r--r--    1 root     root            9 Mar  7 13:03 uplink
-rw-r--r--    1 root     root            8 Jan  1  1970 dhcp_hostname
-rw-r--r--    1 root     root            8 Jan  1  1970 name
-rw-------    1 root     root            8 Mar  7 13:03 restapi_info_shared
-rw-r--r--    1 root     root            7 Jan  1  1970 ap_type
-rw-r--r--    1 root     root            7 Mar  7 13:02 ble_log_level
-rw-r--r--    1 root     root            7 Jan  1  1970 bootcmd
-rw-r--r--    1 root     root            6 Mar  7 15:29 usb_pin_2
-rw-r--r--    1 root     root            4 Jan  1  1970 enforce_uplink
-rw-r--r--    1 root     root            4 Mar  7 13:03 ntpdpid
-rw-r--r--    1 root     root            3 Mar  7 13:03 ap_has_tpm
-rw-r--r--    1 root     root            3 Mar  7 13:03 uplink_dev
-rw-r--r--    1 root     root            2 Jan  1  1970 factory_default_change
-rw-r--r--    1 root     root            2 Mar  7 13:03 factory_mode_print_flag
-rw-r--r--    1 root     root            2 Jan  1  1970 fips_mode.cfg
-rw-r--r--    1 root     root            2 Jan  1  1970 is_rap
-rw-r--r--    1 root     root            2 Mar  7 13:03 ntp_init_state
-rw-r--r--    1 root     root            2 Jan  1  1970 preferred_uplink
-rw-r--r--    1 root     root            2 Mar  7 15:30 usb_present
-rwxr-xr-x    1 root     root            1 Apr  4  2023 fatap
-rw-r--r--    1 root     root            1 Mar  7 13:03 hw_opmode
-rw-r--r--    1 root     root            1 Jan  1  1970 installation_type
-rw-r--r--    1 root     root            1 Mar  7 15:29 meri_sta
-rw-r--r--    1 root     root            1 Jan  1  1970 mesh_enabled
-rw-r--r--    1 root     root            1 Jan  1  1970 mesh_role
-rw-r--r--    1 root     root            1 Mar  7 13:03 ready_for_ipsec
-rw-r--r--    1 root     root            1 Mar  7 13:03 uplink_type
-rw-r--r--    1 root     root            1 Jan  1  1970 usb_port_disable
-rw-r--r--    1 root     root            1 Jan  1  1970 usb_power_override
drwxr-xr-x   19 root     root            0 Mar  7 15:30 .
drwxr-xr-x   15 root     root            0 Jan  1  1970 ..
drwxr-xr-x    2 root     root            0 Jan  1  1970 .papi
drwxr-xr-x    2 root     root            0 Mar  7 15:30 .sock
drwxr-xr-x    2 root     root            0 Jan  1  1970 ap1x_cert
-rw-r--r--    1 root     root            0 Mar  7 13:02 ap_is_up
drwxr-xr-x    2 root     root            0 Jan  1  1970 apfc
-rw-r--r--    1 root     root            0 Jan  1  1970 archerctl.tmp
-rw-r--r--    1 root     root            0 Jan  1  1970 asap.map
-rw-r--r--    1 root     root            0 Mar  7 13:02 auth_surv_debug.log
-rw-r--r--    1 root     root            0 Mar  7 13:02 ble_debug
-rw-r--r--    1 root     root            0 Mar  7 13:03 ble_ready
drwxr-xr-x    2 root     root            0 Mar  7 13:02 blefwdl
-rw-r--r--    1 root     root            0 Jan  1  1970 bond0-eee.log
-rw-r--r--    1 root     root            0 Mar  7 13:03 cellular_history
drwxr-xr-x    7 root     root            0 Jan  1  1970 cert
-rw-r--r--    1 root     root            0 Mar  7 15:28 cgi_err.txt
-rw-r--r--    1 root     root            0 Jan  1  1970 check_ra_flags
srwxr-xr-x    1 root     root            0 Mar  7 13:03 cli_l2tpv3_comm.sock
drwxr-xr-x    2 root     root            0 Mar  7 13:02 core
-rw-r--r--    1 root     root            0 Mar  7 13:03 cparser-error.txt
-rw-r--r--    1 root     root            0 Mar  7 15:30 cpu_util
drwx------    2 root     root            0 Mar  7 13:03 deviceCerts
-rw-------    1 root     root            0 Jan  1  1970 dhcp_ntp_change
-rw-r--r--    1 root     root            0 Mar  7 15:02 dnsip_changed
-rw-r--r--    1 root     root            0 Jan  1  1970 drvlog.map
-rw-r--r--    1 root     root            0 Jan  1  1970 extended_ssid_enabled
-rw-r--r--    1 root     root            0 Mar  7 13:03 fips_kat_done
-rw-r--r--    1 root     root            0 Jan  1  1970 has_ble_support
-rw-r--r--    1 root     root            0 Jan  1  1970 ip_mode_1
-rw-r--r--    1 root     root            0 Jan  1  1970 ipm.map
-rw-r--r--    1 root     root            0 Jan  1  1970 ipv6_capable
-rw-r--r--    1 root     root            0 Jan  1  1970 ipv6_gotip
-rw-r--r--    1 root     root            0 Jan  1  1970 is_uap_platform
-rw-r--r--    1 root     root            0 Jan  1  1970 isl28022.map
-rw-r--r--    1 root     root            0 Jan  1  1970 lldp_sent
-rw-r--r--    1 root     root            0 Mar  7 13:03 loop_debug.log
-rw-r--r--    1 root     root            0 Mar  7 13:03 magic_config
-rw-r--r--    1 root     root            0 Mar  7 13:02 msgh_clear_ips
srwxr-xr-x    1 root     root            0 Mar  7 13:02 msghdlr_comm
-rw-r--r--    1 root     root            0 Mar  7 15:17 mydhcpoption82.xml
drwxr-xr-x    2 root     root            0 Mar  7 15:02 nameservers
drwxr-xr-x    2 root     root            0 Mar  7 15:02 nexthops
-rw-r--r--    1 root     root            0 Mar  7 13:03 ntp.ipc
-rw-r--r--    1 root     root            0 Jan  1  1970 ppp_modules.map
drwxr-xr-x    2 root     root            0 Mar  7 15:29 prov_logs
srwxrwxrwx    1 root     root            0 Mar  7 13:02 redis.sock
drwxr-xr-x   15 root     root            0 Mar  7 15:26 role
srwxr-xr-x    1 root     root            0 Mar  7 13:03 sae_worker_thread0
-rw-r--r--    1 root     root            0 Mar  7 13:03 sapd_lounched
drwxr-xr-x    2 root     root            0 Jan  1  1970 spectrum
drwxr-xr-x   13 root     root            0 Mar  7 15:28 ssid
-rw-r--r--    1 root     root            0 Mar  7 13:02 stm_lounched
srw-rw-rw-    1 root     root            0 Mar  7 13:02 syslogcmd
drwx------    2 root     root            0 Mar  7 13:03 tempCertKey
drwx------    3 root     root            0 Mar  7 13:02 tempEST
-rw-r--r--    1 root     root            0 Jan  1  1970 terminal_access_enabled
-rw-r--r--    1 root     root            0 Mar  7 15:30 usb_protocol_down
-rw-r--r--    1 root     root            0 Jan  1  1970 using_primary_cfg
-rw-r--r--    1 root     root            0 Jan  1  1970 valid_ssid_during_boot
drwxr-xr-x    2 root     root            0 Mar  7 13:03 web_security
-rw-r--r--    1 root     root            0 Mar  7 13:02 wl.map
srwxr-xr-x    1 root     root            0 Mar  7 13:03 wpa_sapd_sock

Core File Directory:
drwxr-xr-x    3 root     root            0 Mar  7 13:02 .
drwxrwxr-x   11 root     root            0 Mar  7 13:03 ..
drwxr-xr-x    2 root     root            0 Mar  7 13:02 previous_core

Config File Directory:
-rwxrwxr-x    1 root     root       275854 Apr  4  2023 ca-bundle.crt
-rwxr-xr-x    1 root     root         9576 Apr  4  2023 setup_ip_swarm
-rwxr-xr-x    1 root     root         4740 Apr  4  2023 probe_pppoe.conf
-rwxr-xr-x    1 root     root         3775 Apr  4  2023 setup_ip
-rwxr-xr-x    1 root     root         3689 Apr  4  2023 setup_pppoe
-rwxr-xr-x    1 root     root         3053 Apr  4  2023 bootstrap_config_download.sh
-rwxr-xr-x    1 root     root         2447 Mar  7 13:03 ntp.conf
-rwxr-xr-x    1 root     root         2341 Apr  4  2023 managed_mode_fixup.sh
-rwxr-xr-x    1 root     root         2281 Apr  4  2023 file_download.sh
-rwxr-xr-x    1 root     root         2254 Apr  4  2023 probe_pppoe
-rwxr-xr-x    1 root     root         1715 Apr  4  2023 replace_default_configuration.sh
-rwxr-xr-x    1 root     root         1497 Apr  4  2023 pppoe.fixup
-rwxr-xr-x    1 root     root         1224 Apr  4  2023 restart_processes
-rw-rw-r--    1 root     root          732 Mar  7 13:03 tinyproxy.conf
-rw-r--r--    1 root     root          548 Jan  1  1970 dhclient6.leases
-rwxr-xr-x    1 root     root          476 Apr  4  2023 launch_pppoe_connect.sh
-rw-r--r--    1 root     root          406 Mar  7 13:03 dnsmasq.conf
-rwxr-xr-x    1 root     root          328 Apr  4  2023 dnsmasq_172.conf
-rwxr-xr-x    1 root     root          326 Apr  4  2023 inittab
-rwxr-xr-x    1 root     root          264 Apr  4  2023 mini_httpd.conf
-rwxr-xr-x    1 root     root          258 Apr  4  2023 mini_httpd_fips.conf
-rw-r--r--    1 root     root          217 Jan  1  1970 resolv.conf.dhclient6
-rwxr-xr-x    1 root     root          197 Apr  4  2023 ppp.fixup
-rwxr-xr-x    1 root     root          192 Apr  4  2023 fatap_pppoe_init.sh
-rwxr-xr-x    1 root     root          190 Apr  4  2023 fstab
-rwxr-xr-x    1 root     root          168 Apr  4  2023 pppoe_conf.fixup
-rw-r--r--    1 root     root          142 Mar  7 15:28 ld_eth_hosts
-rwxr-xr-x    1 root     root          131 Apr  4  2023 fatap_break
-rw-r--r--    1 root     root          116 Mar  7 15:02 resolv.conf
-rwxr-xr-x    1 root     root           64 Apr  4  2023 passwd
-rwxr-xr-x    1 root     root           41 Apr  4  2023 group
-rwxr-xr-x    1 root     root           24 Apr  4  2023 services
-rwxr-xr-x    1 root     root           20 Apr  4  2023 hosts
-rw-r--r--    1 root     root           18 Apr  4  2023 aruba_version
-rw-r--r--    1 root     root           13 Mar  7 13:03 ntpserver.conf
-rw-r--r--    1 root     root           10 Mar  7 13:03 ntpdate.conf
-rwxr-xr-x    1 root     root            6 Mar  7 13:03 TZ
-rw-r--r--    1 root     root            5 Mar  7 13:02 syslogd.pid
-rwxr-xr-x    1 root     root            1 Apr  4  2023 dhclient.conf
drwxrwxr-x    6 root     root            0 Mar  7 15:02 .
drwxr-xr-x   15 root     root            0 Jan  1  1970 ..
drwxrwxr-x   11 root     root            0 Mar  7 13:03 httpd
drwxr-xr-x    2 root     root            0 Jan  1  1970 init.d
-rwxr-xr-x    1 root     root            0 Apr  4  2023 mime.types
drwxr-xr-x    3 root     root            0 Mar  7 13:03 ppp
drwxrwxr-x    2 root     root            0 Mar  7 13:02 ssh

Running processes:
  PID  Uid     VmSize Stat Command
    1 root        524 S   init       
    2 root            SW  [kthreadd]
    3 root            SW  [ksoftirqd/0]
    5 root            SW< [kworker/0:0H]
    7 root            SW  [rcu_sched]
    8 root            SW  [rcu_bh]
    9 root            SW  [migration/0]
   10 root            SW  [watchdog/0]
   11 root            SW  [watchdog/1]
   12 root            SW  [migration/1]
   13 root            SW  [ksoftirqd/1]
   15 root            SW< [kworker/1:0H]
   16 root            SW  [watchdog/2]
   17 root            SW  [migration/2]
   18 root            SW  [ksoftirqd/2]
   20 root            SW< [kworker/2:0H]
   21 root            SW  [watchdog/3]
   22 root            SW  [migration/3]
   23 root            SW  [ksoftirqd/3]
   25 root            SW< [kworker/3:0H]
   26 root            SW< [khelper]
   27 root            SW  [kdevtmpfs]
   28 root            SW< [perf]
   29 root            SW  [kworker/u8:1]
  173 root            SW  [khungtaskd]
  174 root            SW< [writeback]
  176 root            SW< [crypto]
  178 root            SW< [bioset]
  180 root            SW< [kblockd]
  198 root            SW  [skb_free_task]
  199 root            SW< [linkwatch]
  212 root            SW  [kworker/3:1]
  215 root            SW< [kworker/u9:0]
  232 root            SWN [kswapd0]
  317 root            SW  [spi32766]
  418 root            SW  [bpm_monitor]
  420 root            SW  [pdc_rx]
  422 root            SW< [ipv6_addrconf]
  431 root            SW< [deferwq]
  438 root            SW  [ubi_bgt0d]
  445 root            SW  [ubi_bgt1d]
  519 root            SW  [ubifs_bgt1_4]
 3292 root            SW  [fc_evt]
 3298 root            SW  [fc_timer]
 3299 root            SW  [bcmFlwStatsTask]
 3311 root            SW  [bcm_archer_us]
 3338 root            SW  [bcmsw_rx]
 3340 root            SW  [bcmsw_recycle]
 3452 root            SW  [power_monitor]
 3590 root        764 S   usr/sbin/jitterentropy-rngd 
 4446 root            DW  [iapt]
 4553 root         44 S   rdnssd -H /aruba/bin/merge-hook -u root 
 4554 root         52 S   rdnssd -H /aruba/bin/merge-hook -u root 
 4559 root            SW  [kworker/0:3]
 4728 root        192 S   /sbin/udhcpc -i br0 -b 
 5235 root            SW  [kworker/u8:2]
 5402 root       2692 S   /aruba/bin/nanny /aruba/bin/nanny_list 0 
 5416 root       2344 S   /aruba/bin/redis-server 127.0.0.1:0           
 5474 root       1228 S   /aruba/bin/tinyproxy -d 
 5480 root        228 S   /aruba/bin/tinyproxy -d 
 5481 root        228 S   /aruba/bin/tinyproxy -d 
 5482 root       3764 S < /aruba/bin/msgHandler -n 
 5487 root       1552 S   /aruba/bin/syslogd -x -n -m 0 -f /aruba/bin/syslog.co
 5490 root       5664 S N /aruba/bin/awc 
 5493 root      50804 S < /aruba/bin/cli -I 
 5499 root       1212 S   /bin/sh /aruba/bin/cli_console 
 5508 root        516 S   /sbin/klogd -n 
 5522 root        240 S < /aruba/bin/sshd -f /etc/ssh/sshd_config -h /etc/ssh/s
 5527 root       3432 S < /aruba/bin/udmd -s /aruba/bin/udmd_notifier 
 5532 root      10256 S N /aruba/bin/sapd 
 5535 root        232 S   /aruba/bin/wdg 
 5539 root       7468 S < /aruba/bin/stm 
 5552 root        144 S   /aruba/bin/rngd -e 
 5564 root       4040 S   /aruba/bin/snmpd_sap 
 5569 root       5160 S   /aruba/bin/mdns 
 5574 root       1464 S   /aruba/bin/lhm 
 5579 root        568 S   /aruba/bin/resolv_hostname 
 5582 root       2680 S   /aruba/bin/ap_cert_mgr 
 5585 root       2868 S   /aruba/bin/lldpd 
 5588 root       3104 S   /aruba/bin/ctb 
 5591 root       6228 S   /aruba/bin/ble_daemon 
 5626 root       5304 S   /aruba/bin/ble_relay 
 5661 root       3612 S   /aruba/bin/telemetryd 
 5664 root       4312 S   /aruba/bin/off-loader 
 5668 root       2056 S   /aruba/bin/wpa3_sae 
 5717 root            SW< [kworker/u9:1]
 5916 root       2344 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root 
 5925 root       2256 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root -
 5928 root       3488 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root -
 7230 root       1324 S   /bin/sh /aruba/bin/aruba_ntpdate 
 7334 root            RW  [kworker/1:2]
 7422 root      59220 S < dpimgr 
 8238 root       1012 S   ntpd -l /tmp/ntpd.log -p /tmp/ntpdpid 
 8250 root        156 S   /usr/sbin/dhcp-helper -d 
 8251 root       3756 S   /aruba/bin/radiusd -f -d /aruba/radius/raddb 
 8283 root       2724 S < ucm 
10592 root            SW  [kworker/2:0]
11462 root            SW  [kworker/0:1]
20974 root            SW  [kworker/2:1]
23157 root            SW  [kworker/1:0]
24110 root            SW  [kworker/3:2]
25907 root            SW  [kworker/0:0]
27021 root            SW  [kworker/0:2]
27584 root       3656 S   /aruba/bin/radiusd-term -f -d /aruba/radius/raddb-ter
27585 root        200 S   /usr/sbin/dnsmasq -d --server=208.67.222.123 --server
27759 root            RW  [kworker/2:2]
28251 root            SW  [kworker/1:1]
28455 root        520 S   sleep 30              
28931 root       3892 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root -
28952 root       1132 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root -
28953 root       1608 S < swarm.cgi 
28954 root        540 S < /bin/sh -c /usr/bin/debug_memory 1>&2 
28955 root       1300 S < /bin/sh /usr/bin/debug_memory 
28960 root       3688 S N /usr/sbin/mini_httpd -c *.cgi -d /etc/httpd -u root -
28964 root       1620 S < swarm.cgi 
28979 root        532 R < ps              
Mem: 509896K used, 518896K free, 0K shrd, 0K buff, 94276K cached
Load average: 2.75 2.88 2.77  (Status: S=sleeping R=running, W=waiting)
  PID USER     STATUS   RSS  PPID %CPU %MEM COMMAND
 5532 root     S N    10256  5402 13.7  0.9 sapd
 5591 root     S       6228  5402  6.8  0.6 ble_daemon
 7334 root     RW         0     2  6.1  0.0 kworker/1:2
27759 root     SW         0     2  4.0  0.0 kworker/2:2
  212 root     SW         0     2  0.7  0.0 kworker/3:1
 3311 root     SW         0     2  0.4  0.0 bcm_archer_us
 5539 root     S <     7468  5402  0.2  0.7 stm
 5482 root     S <     3764  5402  0.2  0.3 msgHandler
28980 root     R <      512 28955  0.2  0.0 busybox
 3452 root     SW         0     2  0.2  0.0 power_monitor
 3338 root     SW         0     2  0.2  0.0 bcmsw_rx
11462 root     SW         0     2  0.2  0.0 kworker/0:1
28251 root     SW         0     2  0.2  0.0 kworker/1:1
 7422 root     S <    59220  5493  0.0  5.7 dpimgr
 5493 root     S <    50804  5402  0.0  4.9 cli
 5490 root     S N     5664  5402  0.0  0.5 awc
 5626 root     S       5304  5402  0.0  0.5 ble_relay
 5569 root     S       5160  5402  0.0  0.5 mdns
 5664 root     S       4312  5402  0.0  0.4 off-loader
 5564 root     S       4040  5402  0.0  0.3 snmpd_sap
28931 root     S N     3892  5928  0.0  0.3 mini_httpd

CPU Status:
 total: user   2% nice   6% system  14% idle  77% io   0% irq   0% softirq   0%
```