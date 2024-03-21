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