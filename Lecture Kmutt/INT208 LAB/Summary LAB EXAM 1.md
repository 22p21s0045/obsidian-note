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

# Aruba Config LACP
```
aruba# configure terminal

aruba(config)# trunk 13-14 trk1 lacp

aruba# show lacp

aruba# show lacp peer
```


# # Set up VLAN

```
vlan [vlanNumber]
port gigabitethernet 1/0/[portNumber] to g 1/0/[portNumber]
---------------------------------------------------------------------------------
interface gigabitethernet 1/0/[portNumberToAnotherSwitch]
port link-type trunk
port trunk permit vlan [vlanNumber] [vlanNumber]
display vlan all

```

# Aruba Config VLAN
```
configure terminal

C(config)# vlan 100

C(vlan100]# untagged 1-3

C(vlan100]# tagged 14

  

C(config)# vlan 200

C(vlan200)# untagged 4-6

C(vlan200)# tagged 14

show vlan
```
[[Trunk port]]

[[Recap Exam lab 1]]