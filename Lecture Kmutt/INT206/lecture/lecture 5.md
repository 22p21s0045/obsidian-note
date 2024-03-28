#lecture-5 

## What exam about ?
- Lecture 40 ข้อ (choice) 2ชม
- LAB 10 คะเนน
	- เเก้โจท + เขียน Query

[[INT206_07_Distributed_DBMS.pdf]]


## Recap

### Distributed DBMS
- Distributed processing
- Parallel DBMS

### DBMS
- **Homogeneous** ลักษณะเดียวกันผลิตภัณเดียวกัน
- **Heterogeneous** คนลผลิตภัณคุยผ่าน gateway

### Distributed Database Management System (DDBMS) 
is a specialized type of **database management system** that handles data distributed across multiple computers or sites connected by a network. Let’s break down the key points:


### Distributed DBMS
- Fragmentation (เเบ่ง)
	- Horizontal
	- Vertical
- Allocation (ไปวางที่ไหน)
- Replication (reliability)
### Focus
- Locality of reference (เอาข้อมูลไปอยู่ใกล้ๆ ใช้บ่อย)
Store data close to where it is used
- Improved reliability and availability Is improved by replication
- Acceptable performance
Avoid the bottlenecks and underutilization of resources
- Balanced storage capacities and costs
- Minimal communication costs



>[!tip]
>**Complete replication** 
>avalibility are maximize
>Storage is high cost
>High communication


![](https://i.imgur.com/5rMzt7S.png)


![](https://i.imgur.com/3l4rlmt.png)


![](https://i.imgur.com/wY33lou.png)

- Disjoint ไม่มีข้อมูลซั้า
- Completeness
- Reconstruction


![](https://i.imgur.com/PwGHWpz.png)

- เเบ่งเป็น row กับ column


- Location transparency (ระบุ fragment)
- Local mapping tranparency (ระบุ fragment + Site)

![](https://i.imgur.com/o7hHNmo.png)
