# CCNA3 - Chapter 2 -  STP
## Conception
Redundancy enhance availability

Cons :
- Loop -> Broadcast Storm
- Mac table instabiltity
- frame multicast

Behavior :
- 1 logical path
- STP blocked (only enable port for BPDU (Brigde Protocol Data Unit))

Spanning Tree Algorithme  (STA)
- Select Root bridge with Brigde identified by Bridge Id ( Priority+Vlan+SVI @MAC)
- Port Role :
  - Root Port : Indicate the direction to the root Bridge with the best cost
  - Designated Port
  - Blocked Port

  - Send BPDU (with same Bridge ID and root Bridge ID)
- If links have same cost, look port Id (priority, port number), the best is root port, otherwise it's a blocked port

- Hello time : 2 sec
- 2 second to change state

## Variety of Spanning Tree Protocol
- STP (802.1D) : Common Spanning Tree
- PVST+ (Cisco) : Tree by VLAN
- RSTP -> rapid STP (802.1w)
- RPVST+ (Cisco) ->
- MSTP (802.1s) ->Common Spanning Tree for multiple VLAN

## Configuration of Spanning Tree Protocol
- PVST+ / RPVST+ / MSTP
- `spanning-tree portfast` -> enable Peripherical Port
- `spanning-tree bpduguard enable` -> enable guard
- Select primary port or primary switch :
  - `spanning-tree VLAN <vlan_number> root primary`
  - `spanning-tree VLAN <vlan_number> priority <number>`
- `spanning-tree VLAN <vlan_number> root secondary`

## First Hop Redundancy Protocols - FHRPs
- 1 Virtual IP@ and 1 Virtual MAC@ to use multiple router
- 1 Virtual IP@ and Multiple Virtual MAC@ to use multiple router with load balancing
- Send gratuitous to update the port number in ARP Table on switch

Protocols :
- Virtual Router Without LoadBalancing :
  - HSRP (Cisco)
  - VRRP (v2 -> IPv4, v3 -> IPv4+IPv6)
- Virtual Router With LoadBalancing :  
  - GLBP (Cisco)

TP : 2.4.3.4

- `show standby`
- `show glbp`
