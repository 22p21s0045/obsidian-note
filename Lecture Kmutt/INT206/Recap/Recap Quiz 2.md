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