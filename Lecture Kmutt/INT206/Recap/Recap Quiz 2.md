3/12/2024
#recap #quiz
## Errors and Failures
Requiring Recovery from Backup
- Human Errors
-  Media Failures/Disk Failure
- Due to physical damage or a logical failure. Disk failure is probably one of the most common causes of data loss.


>[!tip]
>**DDL** command is auto commit ( CREATE, UPDATE , DROP, ALTER ...)


>[!tip]
>**DML** command is not auto commit (INSERT, DELETE, LOCK)

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