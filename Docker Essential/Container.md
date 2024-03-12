#docker #container
## What are Containers?
- A group of processes run in isolation
- All processes MUST be able to run on the shared kernel
- quickly and reliably across different computing environments.

#compare 
## VM vs Container

![](https://i.imgur.com/tceWeqy.png)

|Aspect|Virtual Machines (VMs)|Containers|
|---|---|---|
|**Isolation**|VMs provide **strong isolation** by running a full OS instance.|Containers offer **lightweight isolation**, sharing the host OS kernel.|
|**Resource Overhead**|VMs have **higher resource overhead** due to running a separate OS for each instance.|Containers are **more resource-efficient**, as they share the host OS resources.|
|**Startup Time**|VMs have **slower startup times** due to booting an entire OS.|Containers start **almost instantly**, as they only need to launch the application process.|
|**Footprint**|VM images are **larger** (GBs) because they include the OS and application.|Container images are **smaller** (MBs) since they only contain the application and dependencies.|
|**Scaling**|VMs can be **scaled vertically** (adding more resources to a single VM) or **horizontally** (adding more VMs).|Containers are ideal for **horizontal scaling**, spinning up multiple instances quickly.|
|**Compatibility**|VMs can run **different OSes** (Windows, Linux, etc.) on the same host.|Containers are **OS-agnostic**, running consistently across different environments.|
|**Use Cases**|VMs are suitable for **legacy apps**, complex setups, and **security isolation**.|Containers are great for **microservices**, cloud-native apps, and **dev/test environments**.|
|**Maintenance**|VMs require **OS patching**, updates, and management.|Containers simplify **maintenance**, as they focus on the application layer.|
|**Density**|VMs have **lower density** (fewer instances per host) due to resource overhead.|Containers achieve **higher density**, allowing more instances on the same host.|
|**Backup/Restore**|VM snapshots capture the entire VM state.|Container images are easily **backed up/restored**, promoting reproducibility.|
|**Security**|VMs provide **stronger isolation**, but vulnerabilities in the OS affect all VMs.|Containers isolate at the **application level**, but shared kernel vulnerabilities are a concern.|
|**Orchestration Tools**|VMs are managed by tools like **VMware**, **Hyper-V**, or **OpenStack**.|Containers are orchestrated using tools like **Kubernetes**, **Docker Swarm**, or **Nomad**.|

