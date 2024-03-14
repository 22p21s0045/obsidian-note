3/14/2024
[[ACL_OSPF_compressed.pdf]]
[Basic OSPF Configuration (networklessons.com)](https://networklessons.com/ospf/basic-ospf-configuration)

#ACL

## Package filtering
- split package


## inbound
- Permit IP from any to any return-traffic
- Permit IP from any to Web-server protocol equal http
- (implicit deny all)
## outbound
- Permit IP from any to any (implicit deny all)
c-z

![](https://i.imgur.com/a2Jq870.png)

## ACL config
```bash
[SW-A] acl number 2000
[SW-A-acl-bas-2000] rule 100 deny source xx.1.1.0 0.0.0.255 [SW-A-acl-bas-2000] rule 200 permit source any
```