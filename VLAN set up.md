
# HP/H3C

```
vlan [vlanNumber]
port gigabitethernet 1/0/[portNumber] to g 1/0/[portNumber]
---------------------------------------------------------------------------------
interface gigabitethernet 1/0/[portNumberToAnotherSwitch]
port link-type trunk
port trunk permit vlan [vlanNumber] [vlanNumber]
display vlan all

```

# Aruba
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

