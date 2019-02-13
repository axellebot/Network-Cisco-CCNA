# CCNA2 - Chapter 8 - OSPF one area
## Caracteristics
- OSPFv1 : never implemented

- OSPF is encapsulated by IP

- Without class (send net mask)
- Efficient
- Safe (security)
- Fast convergence
- Scalable

- Databases :
  - Adjacency  Database :
    - Show neighborhood : `show ip ospf neighbor`
  - LSDB -> Link-State Data Base
    - Show LSDB : `show ip ospf database`
  - Foward database (routing table) : `show ip route`

- Disagnated Router only on multiaccess topology


- All LSP (Link-State Packet) with code to identitfy them :
  - 00x1 -> Hello packet (neighbor detection and contiguity + Parameters + DR Designated Router and BDR Backup Designated Router)
  - 00x2 -> DataBase Description (DBD)
  - 00x3 -> Link-State request (LSR)
  - 00x4 -> Link-State update (LSU) (contains many Link-State Advertisment (LSA))
  - 00x5 -> Link-State Acknowladgement (LSAck)

- Behavior :
  - All Send hello
  - Exchange LSA (contains cost of eache link)
  - Wait same LSB
  - Exec SPF (Shortest Path First) -> Dijkstra
  - Adding to routing table

- If too much routers (CPU consumption, memory consumption, time consumption), use multiple area. (All area are connected to the Federation Area  `#0`)

Sates :
- Etablish contiguity :
  - Down State
  - Init State (send Hello)
  - Two-way State (receive Hello)
- Exchange :
  - Exchange Start State
  - Exchange State
  - Loading State
- Full State

Sending LSA to DR (Designated Router) if connected to multipoint :
- Avoid multiple contiguity
- Avoir massive LSA creation

Synchronisation of Database :
- After Two-way state
- Create master/slave relation (the highest Router ID is master)
- Exchange DBD and Acknowledgements
- Maybe not same data -> Exchange LSR and Acknowledgements

## Config OSPFv2

- Sending LSP in multicast to all `224.0.0.5` to DR with `224.0.0.6`

- `[no] router ospf <pid>` : create ospf process with processId
- `[no] router-id <pid>` : define router id (4 bytes)
  - default 1 -> highest loopback ipv4 `interface loopback`
  - default 2 -> highest ip address from active interfaces
  - need reload or `clear ip ospf <process_id>`
- `[no] priority` : OSPF topology priority
- `[no] passive-interface` : Supress routing updates on an interface
- `[no] auto-cost {reference-bandwidth} <bandwidth>`: change reference bandwidth to calculsate cost  
- `[no] network <net_add> <wildcard_mask> area <area_id>`
- `[no] network <net_add> 0.0.0.0 area <area_id>` : Auto calculate wildcard mask.

Calculate wildcard mask -> invert 1 and 0


OSPF Metric = cost :
cost=ref bandwidth(default 10^8)/interface bandwidth
Hax :
  - Fake bandwidth on interface  `[no] bandwidth <kilobyte/secondes>`
  - Manual add cost `[no] ip ospf cost <cost>`

- Check
  - `show ip ospf neighbor` : check contiguity
  - `shop ip protocols` : show routing protocols
  - `show ip ospf interface [brief]`

## Config OSPFv3
Use IPv6
Use link-local IPv6
- Sending LSP in multicast to all `FF02:05` to DR with `FF02:06`
- Enable router process : `ipv6 router ospf <process_id>`
- Add network to process `ipv6 ospf <ospf_pid> area <areaId>` (default area is 0 )


- Check
  - `show ipv6 ospf neighbor` : check contiguity
  - `shop ipv6 protocols` : show routing protocols
  - `show ipv6 ospf interface [brief]`
