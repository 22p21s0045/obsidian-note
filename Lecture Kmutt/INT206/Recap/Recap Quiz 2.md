3/12/2024
#recap #quiz
## Errors and Failures
Requiring Recovery from Backup
- Human Errors
-  Media Failures/Disk Failure
- Due to physical damage or a logical failure. Disk failure is probably one of the most common causes of data loss.


>[!tip]
>**DDL Data Definition Language **  command is auto commit ( CREATE, UPDATE , DROP, ALTER ...)


>[!tip]
>**DML Data Manipulation Language ** command is not auto commit (INSERT, DELETE, LOCK)

## Back up and Recovery

**Backup**
	- Logfile is **circular fix size**
	- Datafile
- Process of periodically taking a copy of the database and log file (and possibl•:
programs) to offline storage media (disk or tape).
**Journaling / logfile**
- Process of keeping and maintaining a log file (or journal) of all changes made
to database to enable effective recovery in event Of failure.


## Backup Concepts
- What data need to be backed up?
- Location of systems and files to be backed up?
- Who performs backups?
- Time frames for backups?

## Physical Backup
Physical backups consist of<mark class="hltr-yellow"> raw copies </mark>of the directories and files that
store database contents. This type of backup is suitable for large, important
databases that need to be recovered quickly when problems occur.

>[!tip]
>Physical backup is faster than logical backup


## Logical Backup
- Save information with type SQL script
>[!tip]
>Logical backup is ==more flexible== 
>Slower than Physical backup

### restore operation using the MySQL
```sql
mysql -u root -p int206 < [full path]classicmodels_backup.sql
```
## MySQL dump
- **Type:** Logical Backup.
- **Description:** `mysqldump` is a utility tool that performs logical backups by generating a set of SQL statements that can be used to rebuild the original database structure and data. It is commonly used for exporting and creating backups of MySQL databases, making it suitable for scenarios like moving a database from one server to another or creating logical backups for MySQL database

```sql
mysqldump -u [database_username] –p [database_password] [database_name] > [database_backup_file.sql]
```

## MySQL backup
- **Type:** Physical Backup.
- **Description:** `mysqlbackup` is a utility that comes with MySQL Enterprise Backup, offering faster performance compared to `mysqldump`. It is a physical backup solution that supports features like compression, encryption, streaming, partial backups, incremental backups, etc. This tool excels in handling large databases efficiently and provides fast restoration by simply copying files into the data directory without the need for a lengthy import process[


## MySQL import
s a valuable tool for efficiently importing <span style="background:#fff88f">data from text files</span> into MySQL tables, offering flexibility and ease of use for database administrators and users working with MySQL databases
```sql
mysqlimport --user=root --password=tmppassword --columns=empno,ename,job --compress --delete --fields-terminated-by='\t' test employee.txt
```
## Online backup Vs Offline Backup

- Online backup is backup when server is <mark class="hltr-yellow">running</mark> 
		- User can <mark class="hltr-yellow">read only</mark> when online backup is running
- Offline backup is backup when server is offline (<mark class="hltr-yellow">not running</mark>)
	- **Garantee** consistency

## Full backup
This method involves creating a complete copy of the entire data set, including all files, folders, and system configurations. Full backups provide the best protection but are time-consuming and resource-intensive, especially for large datasets. They are typically performed on <span style="background:#d3f8b6">a weekly or monthly</span> basis as part of a comprehensive backup plan

## Incremental backup (Point in time)
This method only backs up <span style="background:#d4b106">the data that has changed since the previous backup</span>, whether it was a full backup or an incremental backup. Incremental backups are faster and use less storage space than full backups, but they can be time-consuming to restore because all previous backups must be applied in sequence to reconstruct the data
- Back up logfile same

## RAID (Redundant Array of Independent Disks)
Performance increasing through <span style="background:#fff88f">data striping</span>
- The data is segmented into equal-size partitions (the striping unit),
which are transparently distributed across multiple disks.
![](https://i.imgur.com/G6PjPvK.png)

- Raid 0 save <span style="background:#fff88f">striping</span> in many disk 
- Raid 1 Mirror
- Raid 5 If <span style="background:#fff88f">one is broken</span> it can recovery

# Transaction
- Logical unit work in database

Transactions in a database system have several benefits, including: **(ACID)**

1. **Atomicity:** Transactions ensure that a group of operations is treated as a single unit of work. If any operation within the transaction fails, the entire transaction is rolled back, and the database is left in its previous state. This ensures that the database remains consistent and reliable. <span style="background:#fff88f">if it abort transaction it abort all sub in transaction</span>
2. **Consistency:** Transactions ensure that the database remains in a consistent state after each transaction. This means that updates to the database are performed in a way that maintains the integrity and validity of the data.
3. **Isolation:** Transactions provide isolation between different operations. This means that each transaction is executed independently of other transactions, ensuring that the results of o<span style="background:#fff88f">ne transaction do not interfere</span> with the results of another.
4. **Durability:** Once a transaction is committed, the changes made by the transaction are <span style="background:#fff88f">permanently saved to the database</span>. This ensures that the data remains accessible and consistent even in the event of a system failure or crash.
5. **Error handling:** Transactions allow for better error handling and rollback capabilities. If an error occurs during a transaction, the entire transaction can be rolled back, ensuring that the database remains in a consistent state.
6. **Concurrency control:** Transactions help manage concurrent access to the database, ensuring that multiple users can access the database simultaneously without causing conflicts or inconsistencies.
![](https://i.imgur.com/4SYs44m.png)


## State of a transaction
- **ACTIVE**
Executes database and non-database operations
- **COMMITED**
	- Transaction is completed
-  **ABORTED**
	- Must be restore to previous state
- **PARTIALL COMMITED**
	- 1. **Data Integrity Checks**:
    
    - The system verifies that the transaction adheres to any defined **constraints** (such as unique keys, foreign keys, and check constraints).
    - It ensures that the transaction doesn’t violate any rules that would lead to inconsistent or incorrect data.
    - For example, if a transaction attempts to insert a duplicate primary key value, it would be rejected.
2. **Replication Checks**:
    
    - If the database is part of a **replication setup** (where data is copied to multiple servers), the system ensures that the transaction can be safely replicated to other nodes.
    - It checks for any conflicts that might arise during replication.
    - For instance, if a transaction modifies data on one node, the system ensures that the same data can be safely applied to other nodes without causing conflicts.
Occurs after the final statement has been executed
It may be found that transaction has violated an integrity constraint
-  **FAILED**
Occurs when transaction cannot be committed or transaction is
aborted
The user might abort the transaction
- The concurrency control protocol might abort the transaction to
ensure serializability


## Transaction Subsystem
![](https://i.imgur.com/I6iNGeh.png)

## Concurrency control
 -  when two or more users are accessing database simultaneously
	- All users are only reading
		- No way to **interfere one another**
		- At least one is updating data
		- May be interfere one another
		- Can result in incong,stencies


## Problem in Concurrency
- Lost update problem
- Dirty read
- Inconsistent analysis problem
	- when a transaction <span style="background:#fff88f">reads several values</span> from a database,<span style="background:#fdbfff"> but another transaction updates some of those values before the first transaction completes</span>. This results in the first transaction reading different values each time it accesses the same row.