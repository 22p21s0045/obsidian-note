#lecture-4 

### Docker pull from registry
```bash
docker pull lvmolarn.sit.kmutt.ac.th/library/ubuntu:latest
```

### List image
```bash
docker image ls
```

### Remove container use image
```bash
docker image rm [imageName] -f
```

>[!tip]
> **Container** ออกเเบบเพื่อให้มีงานหลักอันเดียวเมื่องานหลักเสร็จก็จะตาย

- Nano ไม่สามารถรัน background ได้ (interactive)

>[!tip]
>Container เกิดมาเพื่อรันคําสั่งนั้น เมื่อตาย Container ตาย


```bash
docker run -it ubuntu
```

```
UID          PID    PPID  C STIME TTY          TIME CMD
root           1       0  0 07:27 pts/0    00:00:00 /bin/bash
root          15       1  0 07:29 pts/0    00:00:00 ps -ef
```
- PID 1 ถ้าตาย container ตาย