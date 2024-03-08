- คนมาใช้ร่วมกัน
#problem
## Problem
- Lost update problem (โดนเเย่ง update)
- Uncommit dependency (อ่านข้อมูลที่เก่า)
- Inconsistant analytic system (คํานวณผิดพลาด)
- Phantom read (อ่านค่าเดิมเเต่ไม่ได้ค่าเดิม)

#example

![](https://i.imgur.com/PjZZKoJ.png)


![](https://i.imgur.com/bfq17HA.png)
#serialize-ability
## Serialize ability
- การทํา transaction เป็นลําดับ
- จัด schedule ทําตามลําดับ
	- Serial schedule: (เเต่ละ transaction ทัาตามลําดับ<mark class="hltr-yellow">ห้ามทําพร้อมกัน</mark>) - A **serial schedule** adheres to a straightforward principle: transactions execute **one after the other**, without any interleaving.
	- Non serial schedule: เเต่ละ transaction ทํางานพร้อมกันได้

1. **Read-Only Transactions**:
    
    - When two transactions **only read** data items, they do **not conflict** with each other.
    - The order of execution for read-only transactions is **not important**.
2. **Completely Separate Data Items**:
    
    - If two transactions either **read or write completely separate data items**, they do **not conflict**.
    - Again, the order of execution for these transactions is **not important**.
3. **Read-Write Conflicts**:
    
    - When one transaction **writes** a data item and another transaction **reads or writes the same data item**, their order of execution becomes **important**.
    - Ensuring the correct order prevents **inconsistent** or **unexpected** results.

## Recovery Manager
- สถานะเป็นยังไง recovery ได้มัย
![](https://i.imgur.com/V9umaBi.png)
![Uploading file...xsh9k]()
![[Pasted image 20240307110540.png]]
#locking #method #transaction 
# Locking Method
- Conservative (ไม่ให้ transaction อื่นทํางาน) **ป้องกัน**
	- the prevent transaction lock for another transaction cannot access and unlock when **finish transaction**
- Optimistic เช็คตอนท้ายถ้า conflict <mark class="hltr-yellow">ยกเลิกหมด</mark>
#locking #type
## Type of lock
- **Shared lock** : allow multiple transactions to **read** the same data item simultaneously. (คนอื่นก็สามารถขอ share lock ได้ เเต่ไม่สามรถขอ Exclusive lock)
- **Exclusive lock** : To provide **exclusive access** for writing to a specific part of the data. (transaction เราเท่านั้น)
- Lock ระดับ Row
- Check every time this row have lock ?

## Save Point
- Can roll back to save point
- Not roll back all