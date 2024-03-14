#lecture-3  #transaction #locking
[[Lecture Kmutt/INT206/material/INT206_06_Transaction_Management_Part2_02_2023.pdf|INT206_06_Transaction_Management_Part2_02_2023]]

## Transaction problem
- Lost update
- Dirty read (uncommitted read)
- Inconsistant analysis
## Concurrency control

**Serializability** 
- can be achieved in several ways. Two concurrency control techniques Locking Timestamping

### Serial schedule 
-  Is always a serializable schedule.
-  A schedule where opertions of each transaction are executed consecutive without any interleaved operations from other transactions. 
-  A transaction only starts when the other transaction finished executed
### Non Serial schedule
- Not have order
- Can use parallel

>[!tip]
>If two tranactions either read or write completely separent data items, they<span style="background:#fff88f"> do not conflict</span> and order is not important.

## Recoverability
 is enforced through the use of transaction logs, which record all changes made to the database during transaction processing. When a failure occurs, the system uses the log to<span style="background:#fff88f"> recover the database to a consistent state</span>, which involves either undoing

>[!tips]
>If it have error or crash it auto roll back

1. **Rollback/Undo Recovery Technique:**
    
    - **Description:** This technique involves undoing the changes made by a failed transaction using log records stored in the transaction log.
    - **Functionality:** The system uses these log records to reverse the effects of the failed transaction and restore the database to its previous state.
    
2. **Commit/Redo Recovery Technique:**
    
    - **Description:** This technique is based on reapplying the changes made by a transaction that has committed.
    - **Functionality:** By using log records stored in the transaction log, the system re-applies the changes made by the committed transaction to restore the database to its most recent consistent state

## Cascading rollback
![](https://i.imgur.com/ZZZx7KW.png)

## Timestamp
Not order if conflict it roll back

## Optimistic
- ไม่จัดการ transaction if save check conflict


## Locking
- before edit data must check lock before
- Lock Read/Write
	**Share lock**
		- Read only
    **Exclusive lock**
		- write lock
		- Another transaction can not read/write


>[!tip]
>Locking not enough for serialize database

#new
## Two phase lock (2PL)
- **Phases:**
    
    - **Growing Phase:** In this phase, transactions acquire locks on data items but do not release any locks. The number of locks can only increase during this phase. <span style="background:#fff88f">(ค่อยๆ lock ระหว่าง lock จะไม่มีการปลดล๊อ ล๊อคเฉพาะที่ใช้)</span>
    - **Shrinking Phase:** During the shrinking phase, transactions release locks but do not acquire new locks. Once a lock is released, it cannot be reacquired. <span style="background:#fff88f">(ค่อยๆปลดล๊อค)</span>
- ### Dead lock
	-  Transaction cannot access data
- ### Cascading roll back
	- It is formed using two different words which are cascade and Rollback. The word cascade means, “waterfall” and rollback means, “ an act of making an action to change back to what it was before”. Due to the failure of a single transaction a cascade of transaction rollbacks. This is known as cascading rollback. For instance we can refer to the below mentioned transaction.

## Technique of handling deadlock
- Time out
- Dead lock prevention (analyze it have dead lock ?)
- Dead lock detection (detected before unlock)