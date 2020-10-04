# Cheatography - CCNA4

## Commons

## Serial protocols

- Configure encapsulation:
```
R1(config)#interface <int>
R1(config-if)#encapsulation {ppp|hdlc|framerelay}
```

### PPP (Point to Point Protocol)

- Authentication :
  - CHAP: Password must be the same between routers (random Request ID + hashed password)
  - PAP: Password can be different between routers

- Configure authentication:
```
R1(config)#interface <int>
R1(config-if)#ppp authentication {chap|pap}
```

- Configure PAP between RX and RY
```
R1(config)#username <RY> {password | secret} <word>
R1(config)#interface <int>
R1(config-if)#ppp authentication pap
R1(config-if)#ppp pap sent-username <RX> password <word>
```

- Configure CHAP between RX and RY
```
R1(config)#hostname <RX>
R1(config)#username <RY> {password | secret} <word>
R1(config)#interface <int>
R1(config-if)#ppp authentication chap
```

- Debug PPP
```
debug ppp authentication
```

## WAN

### GRE (Generic Routing Encapsulation)
Private VPN (not specially encrypted) -> tunneling any layer 3 protocol X with any other layer 3 protocol Y

```
R1(config)#interface tunnel <#>
R1(config-if)#tunnel mode gre ip
R1(config-if)#ip address <private@> <mask@>
R1(config-if)#tunnel source <interface#>
R1(config-if)#tunnel destination <remote IP@>
```

Steps :
- Create tunnel
- Change tunnel mode to gre over ip
- Configure tunnel local ip address
- Configure tunnel source/destination (remote ip @)
- Create static/dynamic route

### Routing

Configure eBGP :
```
R1(config)# router bgp <R1 AS-#>
R1(config-router)# network <network ip @>
R1(config-router)# neighbor <next_hop_ip> remote-as <R2 AS-#>
```
