## Big Ball of Mud
1. **No Clear Architecture**: The system lacks a clear architectural vision or design. It often evolves organically, with new features being added without consideration for overall structure.
    
2. **Tight Coupling**: Components within the system are highly interconnected, making it difficult to modify or replace individual parts without affecting others.
    
3. **Spaghetti Code**: The codebase is often messy and difficult to navigate, with tangled dependencies and unclear responsibilities for different modules or classes.
    
4. **Lack of Documentation**: There's often little to no documentation explaining how different parts of the system work together, making it hard for new developers to understand and contribute to the project.
    
5. **Resistance to Change**: Because of the tight coupling and lack of clear design, making changes to the system can be risky and time-consuming. Developers may be hesitant to make modifications for fear of introducing bugs or unintended side effects.
    
6. **Accumulation of Technical Debt**: Over time, the system accumulates technical debt as quick fixes and workarounds are applied to address issues without addressing the underlying architectural problems.


- **Unitary Architecture**
	Unitary architecture, also known as **monolithic** architecture, refers to a system architecture where all components of the system are tightly coupled together and deployed as a single unit. In a unitary
- **Distributed**
	Distributed architecture, on the other hand, refers to a system architecture where components of the system are distributed across multiple nodes or machines, often connected via a network. In a distributed architecture, different components of the system can be deployed and scaled independently, allowing for **greater flexibility and scalability**.


## Architecture Style

### Monolithic style

![](https://i.imgur.com/xC5ibt9.png)

>[!tip]
>ปัจจุบันพยายามเเบ่งออกเป็นส่วนๆ (Container)

- ### Layered
![](https://i.imgur.com/k9MiA1J.png)

>[!tip]
>พยายามเเยก Code เป็นส่วนๆเเต่ละส่วนมีหน้าที่ของตัวเอง

![](https://i.imgur.com/EtijSIc.png)

- ### Pipeline
**Each stage** in the pipeline performs a specific operation on the input data and passes the processed data to the next stage. This pattern is particularly useful for parallelizing and optimizing processing tasks, as well as for organizing complex workflows.
![](https://i.imgur.com/gTuHTXZ.png)

- ### Microkernel (plugin system)
shares similarities with the microkernel architecture in that both involve modularizing a system by separating core functionality from additional features or services.

![](https://i.imgur.com/LmVfAQm.png)

![](https://i.imgur.com/FsJW3Ca.png)
- ### Distributed architecture
![](https://i.imgur.com/Hjr1dmB.png)

>[!tip]
>ควรจะให้ user พอใจกี่ %

- ### Service base architecture
![](https://i.imgur.com/SC5kRGC.png)
![](https://i.imgur.com/1q6U474.png)

- ### Event driven
Asynchronous style

![](https://i.imgur.com/vl8NkgN.png)
