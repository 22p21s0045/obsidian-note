
```js
configure terminal
trunk [portNumber]-[portNumber] [trunkGroupName] lacp
```

# Show Lacp

```
show lacp peer
```
output
![[Pasted image 20240302102526.png]]
# **Mode**
The current LACP operation mode of the local port:
* <mark style="background: #FFF3A3A6;">**Passive</mark>:** The switch waits for the peer device to initiate LACP negotiation. 
* <mark style="background: #FFF3A3A6;">**Active:**</mark> The switch actively initiates LACP negotiation with the peer device.