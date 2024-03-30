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


### atomicity
- If it error it rollback if success it commit it have only two state

### durability
- If commit it must save to database data is not lost


## Control technique
- Locking
- TimeStamp
	### **Locking Method**
		- Share lock  (another transcation read only)
		- Exclusive lock (another transaction can not read and write)