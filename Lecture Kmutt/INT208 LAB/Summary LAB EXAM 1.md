# LACP setup
1. First select bridge aggregation group
2. Turn on LACP

[[Link Aggregation (LAG)]]
```
interface bridge-aggregation [groupNumber]
link-aggregation mode dynamic
```

Add port to LAG(link aggregation group)
```
interface GigabitEthernet 1/0/[portNumber]
port link-aggregation group [groupNumber]
display link-aggregation verbose
```
![[Pasted image 20240228142018.png]]

Aruba Config LACP
```
aruba# configure terminal

aruba(config)# trunk 13-14 trk1 lacp

  

aruba# show lacp

aruba# show lacp peer
```