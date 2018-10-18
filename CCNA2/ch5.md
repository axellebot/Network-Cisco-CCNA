# Chapitre 5 - Routage inter-VLAN
`no switchport`
With router : "Routeur-on-a-strick" to use sub-interface -> use only 1 physical interface for many vlan on router
With switch (with layer 3) : configure SVI
## Configuration du routage inter-VLAN

```
interface g0/0.10
encapsulation dot1q 10
ip address 172.17.10.1 255.255.255.0
interface g0/0
no shutdown
```

## Dépannage du routage inter-VLAN
Use of ICMP and traceroute

Config trunk switch port to the router

```
show interfaces FastEthernet 0/4 switchport
show ip interface
```

Proxy ARP can be implemented on router and answer to non answered ARP request

- VLAN
  - VLAN must be defined on all switches
  - VLAN must be authorized on trunk ports
  - Switch ports must be configured on right Vlan
- SVI
  - SVI interface must have an ip address
  - SVI must be config with VLAN
  - SVI must be configured

## Commutation de couche 3

## Resume
