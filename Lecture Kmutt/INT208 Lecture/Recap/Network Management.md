## FCAPS
- **Fault**: Managing and identifying issues within the network.
- **Configuration**: Overseeing the setup and adjustments of network components.
- **Accounting**: Tracking network usage data for billing or analysis purposes.
- **Performance**: Monitoring and improving network performance.
- **Security**: Protecting the network from unauthorized access and threats.

## SNMP
SNMP is a protocol used for **network management** to monitor network-attached devices for conditions that warrant administrative attention.

- SNMP is like a set of **standardized question**s a teacher (NMS) can ask the students to get information about their progress (device status).
- The teacher then collects these answers, analyzes them, identifies any students who might be struggling, and takes necessary actions.
- MIB acts like a **dictionary** for network devices. It defines the data available on the device, what each piece of data represents (e.g., CPU temperature, memory usage, interface errors), and how it's organized.


## Radius
- RADIUS is a protocol that provides centralized authentication, authorization, and accounting (AAA) for network access.
- It works by having a network device (like a router or switch) communicate with a RADIUS server to **verify a user's credentials** (username and password) before granting access to the network.
- RADIUS doesn't store user credentials itself, it relies on another service like LDAP for that.

>[!tip]
>  Open on port **1812-1813**

## LDAP
The LDAP server is a directory service, such as Microsoft Active Directory, OpenLDAP, or FreeIPA, that stores usernames and passwords in the form of an LDAP directory tree.


## AAA (Authentication Authorization Accounting)

[Authentication](https://www.strongdm.com/authentication) is the process of **identifying a user** and granting them access to the network. Most of the time, this is done through traditional username and password credentials. However, users could also use [passwordless authentication](https://www.strongdm.com/blog/passwordless-authentication) methods, including biometrics like eye scans or fingerprints, and hardware such as hardware tokens or smart cards.
-  Authorization
After authentication, the authorization process enforces the network policies, granular access control, and **user privileges**. The cybersecurity AAA protocol determines which specific network resources the user has **permission to access**, such as a particular application, database, or online service. It also establishes the tasks and activities that users can perform within those authorized resources.

- Accounting
**Monitoring activity** of user

[[wire-less]]



