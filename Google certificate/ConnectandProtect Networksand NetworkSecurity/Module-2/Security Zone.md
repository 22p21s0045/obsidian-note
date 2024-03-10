#subnet
## Subnet
- Can devide network

## Controlled zone
- Protect the internal network from the uncontrolled zone
		**DMZ (demilitarize zone)**  creates a secure middle ground where external services can interact with the internet while safeguarding the organization’s internal network.
		**Internal Network**
		**Restricted zone**

![](https://i.imgur.com/7HNaTDC.png)

#tips #subnet 
## What is CIDR (Classless Inter-Domain Routing or supernetting)?

CIDR (Classless Inter-Domain Routing or supernetting) is a method of assigning [IP](https://www.techtarget.com/searchunifiedcommunications/definition/Internet-Protocol) addresses that improves the efficiency of address distribution and replaces the previous system based on Class A, Class B and Class C networks.

The initial goal of CIDR was to slow the increase of [routing tables](https://www.techtarget.com/searchnetworking/definition/routing-table) on routers across the internet and decrease the rapid exhaustion of IPv4 addresses. As a result, the number of available internet addresses has greatly increased.

The original classful network design of the internet included inefficiencies that drained the pool of unassigned IPv4 addresses faster than necessary. The classful design included the following:

- Class A, with over 16 million identifiers
- Class B, with 65,535 identifiers
- Class C, with 254 host identifiers