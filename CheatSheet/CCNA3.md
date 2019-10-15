# Cheatography - CCNA3

## Spanning Tree
- Toggle ST : `[no] spanning-tree`
  - Set root : `[<vlan#> root {primary|secondary}]`
  - Edit link cost : `[no] spanning-tree cost <value>`
  - Edit mode `spanning-tree mode {rapid-pvst|pvst}`
- `show spanning-tree` : show spanning tree protocols info

## EtherChannel
- Set EtherChannel group : `[no] channel-group <group#> mode {active|auto|desirable|on|passive}>`
- Force EtherChannel : `[no] channel-group <group#> mode on`
- EtherChannel negociation with PAgP : `[no] channel-group <group#> mode {auto|desirable}`
- EtherChannel negociation with LACP : `[no] channel-group <group#> mode {active|passive}`

- Change prompt to channel `interface port-channel <number>`

- Disable interface before configuring EtherChannel
- `show interface port-channel <channel#>`
- `show etherchannel summary`
- `show etherchannel port-channel` :
- `show interface etherchannel` : Interface's role in etherchannel

## OSPF
- Single area OSPF -> only area 0
- Multiple area -> All area must be connected to area 0

- Create IPv4 OSPF and defining OSPF network :
```
Router(config)#router ospf <process-number>
Router(config-router)#router-id <ip-address>
Router(config-router)#network <address> <wildcard-mask> area <area-number>
```

- Create IPv6 OSPF and defining OSPF network :
```
Router(config)#ipv6 router ospf <process-number>
Router(config-router)#router-id <ip-address>
Router(config-router)#area <area#>
Router(config)#interface <interface_id>
Router(config-if)#ipv6 ospf <process_id> area <area#>
```

- Enable MD5 authentication :
```
Router(config)#[ipv6] router ospf <process-number>
Router(config-router)#area <area-id> authentication message-digest
Router(config)#interface <interface_id>
Router(config-if)#ip ospf message-digest-key <key-id|{1}> md5 <secret>
```

- Change interface priority :
```
Router(config-if)#{ip|ipv6} ospf priority <0-255>
```

- Change interface cost :
```
Router(config-if)#{ip|ipv6} ospf cost <cost>
```

- Config intervals :
```
Router(config-if)#ip ospf {hello-interval | dead-interval} <seconds>
```

-  reload ospf process : `Router#clear ip ospf process`

- Show  OSPF informations :
  - `show {ip|ipv6} ospf neighbor` : show neighbor list
  - `show {ip|ipv6} ospf interface` : Show ospf configured interfaces

## EIGRP
EIGRP can be configured with custom "Autonomous system number" (1-65535) :

- Enable EIGRP process :
```
[no] [ipv6] router eigrp <IAS#>
[no] shutdown
```

- change router-id :
```
router eigrp <IAS#>
eigrp router-id <router_id>
```

Summary :
- `[no] auto-summary` : toggle automatic network number summarization
- Add ip summarization :
```
Router(config-if)#ip summary-address eigrp <eigrp_AS#> <net_ip> <net_mask>
```

- Propragate route : `redistribute {static|}`

-  MD5 Authentication :
```
Router(config)#key chain <chain_name>
Router(config-keychain)#key <id>
Router(config-keychain-key)#key-string <key_string>
Router(config-if)#{ip|ipv6} authentication mode eigrp <IAS#> md5
Router(config-if)#{ip|ipv6} authentication key-chain eigrp <IAS#> <key_chain_string>
```

- `show {ip|ipv6} eigrp interface` : Show ospf configured interfaces

## IOS Images
- Show flash : `show flash`
- Copy tftp to flash `copy tftp: flash:`
- Load image : `boot system {tftp|flash} <file> `
