# EIGRP (Enhanced Interior Gateway Routing Protocol)
## Caracteristics of EIGRP

- Link State protocol
- 1992 Cisco proprietary protocol
- DUAL Algorithm (calculate path and backup path)
- Etablish neighbor Adjancies

Behavior for each protocols (IPv4 and IPv6) :
- Neighbor table
- topology table
- Routing table

Use own transport protocol -> RTP (replace TCP)

IP PDU type :
- Hello
- ACK
- Update
- Request (Ask missing data/verify data)
- ICMP (used to Answer)

Hello packets :
- Multicast : 224.0.0.10 | FF02::A
- Waiting time, 3 times hello

Update packets :
- Send changed informations

Encapsulated : MAC header | IP header | EIGRP header | Type TLV
with EIGRP header : | Version +Code OP+ Checksum | Indicator | Sequence | ACK | Autonomous system ID  |

Autonomous system ID (not global with IANA) : auto managed areas and have to use External Protocol :
- `router eigrp <autonomous-system>` : same  autonomous-system ID on all router in the same area
- Announcing network : Without mask it can announce multiple network cause of old class behavior

```
router eigrp <autonomous-system>
eigrp router-id <ID>
network <@NETORK-IP> [@IP-WILDCARD-MASK]
```

Check EIGRP config :
- `show ip eigrp neighbors` : Show neighbors
- `show ip protocols` : All routing protocols infos
- `show ip route` : (D-DUAL)

## Behavior
- Metrics :
  - Bandwidth (smallest of all links of the path in kb/s) -> 10 000 000 /smallest bandwidth
  - Delay (sum of all delay on path) -> sum of delays/10
  - Fiability
  - Charge
- EIGRP metric On basic behavior, total -> (bandwith+delay) * 256 = EIGRP metric)
- Fiability with Fiability and charge
```
router eigrp <autonomous-system-id>
metric weights ...
```

## DUAL (Diffusing Update Algorithm)
Used to calculate Backup route

Successor and feasibility distance
- Feasibility Successor (FS) : Neighbor having backup path without loop to the same network anounced by the successor and fulfils Feasibity Condition
- Feasibility Condition (FC) : is fulfiled when annonced distance (RD) of a neighbor
// TODO

Mode debug : `debug eigrp fsm`
