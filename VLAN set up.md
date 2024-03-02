
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
```js
aruba# configure terminal
aruba(config)# vlan 100
aruba(config-vlan 100)# untagged 1-2
aruba(config)# vlan 200
aruba(config-vlan 200)# untagged 5-6
aruba# show vlan 100
aruba# show vlan 200

```

output:
```
VLAN Name Status Ports 
------ ---------- -------- 
100 Active Gi0/1, Gi0/2, Fa0/0 (untagged)
```