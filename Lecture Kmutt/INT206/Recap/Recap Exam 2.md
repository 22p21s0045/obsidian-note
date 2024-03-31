#transaction 
## Transaction Management

- **Seriability** (ทําเป็นลําดับ)
- **Recoverability** (สามารถ Recover ได้)

	<span style="background:#b1ffff">Schedule</span>
 It is manger to manage **sequence**
	- Serial schedule (ตามลําดับ)
		-
	- Non serial schedule (ไม่ตามลําดับ)
		-  It can read write parallel but it can appear **dirty read**

>[!tip]
>• If one transaction writes a data item and another reads or writes same
data item, order  execution is important.

>[!tip]
>Cascading rollback if this transaction read another transaction but another is rollback
### atomicity
- If it error it rollback if success it commit it have only two state

### durability
- If commit it must save to database data is not lost
### Consistency

ensures that any transaction will bring the database from one valid state to another

คือคุณสมบัตที่จะต้องแน่ใจได้ว่า ไม่ว่า transaction จะทำถึงกระบวนการไหน ข้อมูลจะต้องถูกเขียนลงบน database อย่างถูกต้องตามกฎที่ตั้งไว้ แต่ไม่ได้หมายความว่าผลลัพธ์จะได้ถูกต้องตามที่ application หวังเอาไว้ เพราะเป็นความรับผิดชอบระดับ code ของ application เองที่จะต้องรองรับตาม logic


## Control technique
- Locking
- TimeStamp
	### **Locking Method**
		- Share lock  (another transcation read only)
		- Exclusive lock (another transaction can not read and write)
	##Two phase locking
		 **(Dead lock)**
		 ในการล็อคข้อมูลถึงแม้เราจะสามารถแก้ปัญหาต่างๆ ที่ทำให้เกิดความไม่ถูกต้องของข้อมูลได้ก็ตาม แต่ถ้าการล็อคข้อมูลแต่ละ Transaction ไม่สัมพันธ์กันแล้วจะส่งผลให้เกิดปัญหาที่ แต่ละ Transaction ต่างฝ่ายต่างล็อคข้อมูล จะทำให้ทั้งสองฝ่ายไม่สามารถทำงานต่อไปได้ครับ เนื่องจากทั้งสองฝ่ายต่างก็รอให้อีกฝ่ายปล่อยล็อคข้อมูลก่อนนั้นเอง
			 - Timeouts
			 - Deadlock prevention (ยังไม่เกิด) 
			 - Deadlock detection (เกิดเเล้ว)


## Database Recovery

- **Redo**: Reapplies committed changes after system failure using transaction logs. Undo: 
- **Rolls back** uncommitted or aborted changes to maintain data consistency.


>[!tip]
>Incremental backup involves backing up only the changes made since the last backup, minimizing storage space and backup time.


## Distributed database

- transparency (มองผ่านไปเหมือนว่า database  อยู่ที่เดียว)
- Fragment (ส่วนของข้อมูล)
### Parallel Database Management System
type of database management system that is designed to process queries and  transactions concurrently across **multiple processing units** or nodes. In a PDBMS, data is distributed across these processing units

### Advantage of distributed DBMS
- Reflects organizational structure
- Improved shareability and local autonomy
- Improved availability
- Improved reliability
- Improved performance
- Economics ประหยัด
- Modular growth เพื่มขยาย