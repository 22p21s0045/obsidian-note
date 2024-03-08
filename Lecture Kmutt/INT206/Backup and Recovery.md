![[Pasted image 20240229094802.png]]

- Copy data and log file (optional)

Why Log file is <mark style="background: #FF5582A6;">important</mark>
- สามารถเช็คได้ว่ามีข้อมูลล่าสุดเท่าไหร่
- Log file  (เก็บทับข้อมูลเดิม มันจะไม่โตขึ้นเรื่อยๆ)
- ควรจะ backup log file เสมอ
- Journal = Log file


# **Improved Efficiency:**

- **Full backups:** Running frequent full backups can be resource-intensive and time-consuming, impacting system performance.
- **Log backups:** They are significantly smaller and quicker to perform compared to full backups. This allows for more frequent backups without compromising system performance, offering a **balance between data protection and efficiency**.
[[Physical backup]]
[[Logical backup]]
# Tools
- MySQL Backup tool [[Physical backup]]
- MYSQL Dump tool [[Logical backup]]
- MYSQL import tool

Online Backup
- Backup when database is running
- User can<mark style="background: #FF5582A6;"> read only</mark>

Offline Backup
- Backup when database is turn off
- **Guaranteed consistency


# Full backup
- Back up ทั้งหมด
- นานๆที backup

# Incremental backup
- Back up เฉพาะส่วนที่ต่างกับ Full backup ล่าสุด

# Recovery concepts
- คุ้มค่ามั๊ยที่จะทํา

# System Crash
- System down
- DBA should restart database. <mark style="background: #FFF3A3A6;">DBMS</mark> is auto recovery data
- It read log file
- If user not commit it auto roll back

[[Raid technology]] is Another staregy
