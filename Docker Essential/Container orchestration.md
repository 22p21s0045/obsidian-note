#orchestration #docker #docker-swarm
![](https://i.imgur.com/nHIwMRN.png)

**Container orchestration** is the automation of various operational tasks involved in <span style="background:#fff88f">running containerized</span> workloads and services. It includes provisioning, deployment, scaling, networking, load balancing, and more to manage a container's lifecycle efficiently

![](https://i.imgur.com/C4qytfX.png)

## LAB

```bash
docker swarm init --advertise-addr eth0
```

##  `--advertise-addr`#

	To put it simply, the `--advertise-addr` is the address other nodes in the Docker swarm use to connect into your node. You need to provide an IP address of your host, or a network interface which Docker will use to lookup your IP address, and a port number which defaults to 2377:



```bash
docker service update --image nginx:1.13 --detach=true nginx1
```

- Update version nginx to another worker

**Docker Swarm** cluster consists of one master and two worker nodes, which is not highly available. If the manager node goes down, the cluster will cease to function. For production applications, it's recommended to provision a cluster with multiple manager nodes to tolerate manager node failures.

- Three manager nodes tolerate one node failure .
- Five manager nodes tolerate two node failures  .
- Seven manager nodes tolerate three node failures .



