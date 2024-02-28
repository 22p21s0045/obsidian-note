- **Function:** LAG is the **actual process** of combining multiple physical network ports into a single **logical link**. This essentially bundles the **bandwidth** and capabilities of the individual ports, creating a higher bandwidth connection.
- **Benefits:**
    - **Increased bandwidth:** The combined bandwidth of all member ports becomes available to the logical link.
    - **Fault tolerance:** If one physical port in the LAG fails, the remaining ports can still carry traffic, ensuring uninterrupted communication.
    - **Load balancing:** Traffic can be distributed across the member ports, improving network performance.
- **Types:**
    - **Static LAG:** Manually configured by the network administrator. Requires precise configuration on both ends for successful operation.
    - <mark style="background: #FF5582A6;">**Dynamic LAG</mark>:** Uses the **LACP** protocol for automatic negotiation and configuration between switches.

![[Pasted image 20240228140025.png]]
`display link-aggregation verbose` 
Port Status: <mark style="background: #FFF3A3A6;">S -- Selected, U -- Unselected</mark>, I -- Individual
Flags:  A -- LACP_Activity, B -- LACP_Timeout, C -- Aggregation,
        D -- Synchronization, E -- Collecting, F -- Distributing,
        G -- Defaulted, H -- Expired

[display link-aggregation verbose (hpe.com)](https://techhub.hpe.com/eginfolib/networking/docs/switches/5920-5900/5998-5320a_l2-lan_cr/content/414638748.htm)
# LACP Makes Data Transmission More Stable and Reliable

In manual mode, all links are active links and forward data in load balancing mode. If one active link fails, traffic is load balanced among the remaining active links.

In LACP mode, active and backup links are selected. This mode is also called M:N mode, where M refers to the number of active links and N refers to the number of backup links. This mode guarantees high link reliability and allows traffic to be load balanced among active links.