#lecture-4 #locking #database-recovery
[[INT206_06_Transaction_Management_Part2_02_2023.pdf]]
## Recoverable Schedule

### Dead lock time out
- ถ้า transaction ยาวก็จะมีปัญหา
### Dead lock detection


>[!tip]
>If database not commit or rollback it not consistency


## Database Recovery
Definition:
	Process of restoring database to a correct state in the event of a
	failure.
- Transactions represent basic unit of recovery.
- Recovery manager responsible for **atomicity** and
  durability.



### Types of Failures
- **System crashes**, resulting in loss of main memory.
- **Media failures**, resulting in loss of parts of secondary
  storage.
- Application software errors.
- Natural physical disasters.
- **Carelessness** or unintentional destruction of data or
  facilities.
- Sabotage.

>[!tip]
>**redo** if you commit yet and want to undo
>**undo** rollback if you not commit yet


- Partial undo ยกเลิกอันเดียว
- Global undo ยกเลิกหมดเลย

![](https://i.imgur.com/baMlS5T.png)


- ถ้า t1 , t6 roll back t2,t3,t4,t5 หาย เเต่ tc เป็น checkpoint t2,t3 ไม่ต้องทํา


## Log File
- Contains information about all updates to database:
- Transaction records.
- Checkpoint records.
- Log is save fast


## Recovery technique
If database has been damaged: Need to restore last backup copy of database and reapply
updates of committed transactions using log file.


![](https://i.imgur.com/MmmcXhR.png)

- Full backup
- Incremental Monday
- Incremental Tuesday
- Logfile


# Distributed DBMS
## Concepts.
	- Advantages and disadvantages of distributed databases.
	- Functions and architecture for a DDBMS.
	- Distributed database design.
	- Levels of transparency.
	- Comparison criteria for DDBMSs.


## Distributed Database
A logically interrelated collection of shared data (and a
description of this data), physically **distributed over a**
**computer network**.

![](https://i.imgur.com/fGxnMfV.png)

>[!tip]
>พยายามเอาข้อมูลเข้าไปใกล้ user

**Fragment** = ส่วนของข้อมูล

## Advantage of distributed DBMS
- Reflects organizational structure
- Improved shareability and local autonomy
- Improved availability
- Improved reliability
- Improved performance
- Economics ประหยัด
- Modular growth เพื่มขยาย

## Disadvantages of DDBMSs
- Complexity
- Cost
- Security
- Integrity control more difficult (เเต่ละที่สามารถจัดการได้ด้วยตัวเอง customize)
- Lack of standards
- Lack of experience
- Database design more complex

## Homogeneous DDBMSs
**All sites use same DBMS product.** Much easier to design and manage.
Approach provides incremental growth and allows increased performance.
## Heterogeneous DDBMSs
Sites may run **different DBMS products,** with possibly different
underlying data models. Occurs when sites have implemented their own databases and
integration is considered later. Typical solution is to use **gateways**, which convert the language and model of each different DBMS into the language and model of
the relational system.


## Federate table

![](https://i.imgur.com/VvgL8bc.png)
- สร้าง link ไปหา อีก server

### Create link
```sql
CREATE SERVER parislink
FOREIGN DATA WRAPPER mysql
OPTIONS (USER 'dba01', PASSWORD 'int206', HOST '188.166.216.13', PORT 3306, DATABASE 'classicmodels');


DESCRIBE employees;employees

```

### Create table and use link
```sql
CREATE TABLE `classicmodels`.`office_paris` (
  `officeCode` INT NOT NULL,
  `city` VARCHAR(50) NOT NULL,
  `phone` VARCHAR(50) NOT NULL,
  `addressLine1` VARCHAR(50) NOT NULL,
  `addressLine2` VARCHAR(50) NULL,
  `state` VARCHAR(50) NULL,
  `country` VARCHAR(50) NOT NULL,
  `postalCode` VARCHAR(15) NOT NULL,
  `territory` VARCHAR(10) NOT NULL,
  PRIMARY KEY (`officeCode`))
ENGINE=FEDERATED
DEFAULT CHARSET=utf8mb4
CONNECTION='parislink/offices';

```

![](https://i.imgur.com/E7Tes7j.png)
- เก็บ metadata ของ database ว่า data อยู่ที่ไหน มีโครงสร้างอะไรบ้าง

![](https://i.imgur.com/PJQO5rQ.png)
- จักการ local database


![](https://i.imgur.com/B9hV29B.png)
