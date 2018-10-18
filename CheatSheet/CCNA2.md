# Cheatography - CCNA2
## Switch - Security
- Enable SSH v2 `ip ssh version 2`
- Set mode on switch port : `[no] switchport mode [access|trunk]`
- Set the native vlan: `switchport native vlan 99`
- Enable port security : `[no] switchport port-security`
  - Set secured mac address : `switchport port-security mac-address [H.H.H.H|sticky]`
  - Set maximum mac address on the port : `switchport port-security maximum [# of authorized devices]`
  - Set violation rule : `switchport port-security violation [protect|restrict|shutdown]`

## Misc
- Config interface 3 to 24 : `interface range FastEthernet 0/3 - 24`

- Show port security info : `show port-security [address|interface]`
- Show global or interface switchport config  : `show interfaces [interface] switchport`
- Show VLAN config : `show vlan [brief]`
- Show trunk config : `show interface trunk`

Database manager of switch : "SDM (Switch Database Manager)"

## Inter-VLAN
- Show type of switchport `show interface feastEthernet 0/4 switchport`
- Set encapsulation on interface : `encapsulation [protocol] [vlanId]`
- Disable switchport and enable routed port : `no switchport`
