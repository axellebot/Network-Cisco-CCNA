# CCNA4 - Chapter 5 - Network monitoring and security

## LAN security
Basics :
- CDP
- Telnet
- Flooding MAC table
- VLAN (ex: TDP)
- DHCP (ex: Starving)

### CDP (Cisco Discovery Protocol)
- Disable CDP: `no cdp run`

### Telnet:
- Force password
- DoS Telnet

Counter :
- Use SSH
- Strong password
- Add ACLs
- Use AAA (TACACS+ / RADIUS)

### Flooding MAC table
Counter:
- Limit port address per port
- Fixed port address to 1

### VLAN
- Create trunk with DTP

Counter:
- Disable trunk negociation
- Manually configure access port (`switchport mode access`)
- Change native VLAN

### DHCP
- DHCP Spoofing (replace DNS server)
- DHCP Starvation

Counter:
- Configured monitoring with DHCP snooping
- Configure port security

### Security

- Port security
- DHCP snooping
- Inspect ARP dynamic
- IPSG

- Authenticate management connection (AAA with RADIUS + TACACS+ )
- Authenticate use connection (802.1X with RADIUS)

## SNMP
- SNMP manager
- SNMP agent
- MIB (Management Information Base)

Message types :
- Trap (v1) / Notify (v3)
- GET
- SET
```
snmp-server community <> <ro> <ACL>
snmp-server location <txt>
snmp-server contact <txt>

# traps
snmp-server host <host-ip-adress> [version {1/2c/3 [auth | nooauth | priv]}]
snmp-server enable traps <notification-types>
```

## SPAN (Switch Port Analyzer)

Mirroring port :
- Analyzed packets
- Analyze intrusion

Forward traffic (to local or remote listener)
Configure :

```
monitor session <#> source {intercace <int> | vlan <vlan#>}
monitor session <#> destination {intercace <int> | vlan <vlan#>}
```
