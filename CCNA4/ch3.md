# CCNA4 - Chapter 3 - Division connection

## Remote connection
- Cable
- XDSL
- FTTH
- Wifi Mesh
- Cellular
- Satellite

## PPPoE

MTU: Maximum Transmission Unit
MSS: Maximum Trans
```
interface dialer <#>
encapsulation ppp
ip address optionnal

ppp chap username <username>
ppp chap password <pwd>

dialer pool 1
noshutdown

interface <int>
no ip address
pppoe enable
pppoe-client dial-pool-number 1
```

```
show pppoe session
```

```
interface dialier 2
mtu 1492
interface g0/0
ip tcp adjust-mss 1452
```

## VPN
- Side to side
- Road wired (remote access)

## GRE (Generic Routing Encapsulation)
Private VPN (not specially encrypted) -> tunneling any layer 3 protocol X with any other layer 3 protocol Y

```
interface tunnel <#>
tunnel mode gre ip
ip address <private@> <mask@>
tunnel source <interface#>
tunnel destination <remote ip @>
```

## eBGP
Routing protocol family
- EGP (eBGP)
- IGP (iBGP)

Configure routing:
```
(config)#router bgp <as-number>`
(config-router)#neighbor <ip-adress> remote-as <other-as-number>`
(config-router)#network <network-address> [mask <network-mask>]`
```

- Show bgp summary : `show ip bgp summary`
