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
Save information with type SQL script
>[!tip]
>Logical backup is ==more flexible== 


