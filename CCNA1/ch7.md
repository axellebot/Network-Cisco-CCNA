# Chapter 7

## IPV4

## IPV6
Coexistance between IPV4 and IPV6 :
- Dual Stack
- Tunneling (The fact to encapsulate the protocol of the same level) IPV6 in IPV4
- Translation NAT64 (Network Address Translation 64) : IPV4 <-> IPV6

IPV6 Address (8 Hextet) rules :
- Removed extra 0 at the beginning
- Replace "0:0:0" by "::" (once) -> Compressed format

Type of IPV6 address :
(No more Broadcast)
- Unicast
- Multicast
- Anycast (reach the nearest from a group)

- Subnet mask with '/'

### Unicast
IPV6 Unicast Addressing :
- Global Unicast : public address
- Link-local : only in 1 subnet (on the same link) `FE80::/10` -> `FEBF::/10`
- Loop : `::1/128` :
Send to his self
- Non specified address : `::/128`
Used when address unknown
- unique local : `FC00::/7` -> `FDFFF::/7` (private address) :
- integrated IPV4 :
Used to translate

#### Link-local Unicast
- Unique in 1 subnet
- Mendatory address set staticly or dynamicaly
- 10 first bits to 1111 1110 10xx xxxx -> `FE80::/10` -> `FEBF::/10`

#### Glboal Unicast
- Needed to reach WAN
- IANA with ICANN  give bucket of address

Structure :
- Global Routing prefix (48bits)
- subnet ID (16 bits)
- interface ID (63 bit)

- 4 hextet : global routing prefix + subnet id
- 4 hextet : interface ID

##### SLAAC (State Less Address Auto Configuration)
Set Dynamicaly Global unicast. No data saved ("State Less").
- Get metadata from the router (RA Router Announcmenet / RS Router Solicitation) :
  - Prefixe, with lenght
  - Default Gateway Address
- Generate interface ID :
  - Based on MAC address
  - Random
- No need DHCPv6
- Based on ICMPv6

##### IPV6 routers :
Use IPv6 link local for the next hop.
- Foward IP fragment
- Can be configured with static and dynamic routes
- Send RA ICMPv6
- Enable with cmd : `IPv6 unicast routing`
- Can send announce option :
  - SLAAC (all)
  - stateless DHCPv6 : Router (prefix, default gateway) + DHCPv6 (DNS)
  - Statefull DHCPv6 (all)
- Announce with link-local (default gateway for the host)

##### Host generation
The host generate its own global address :
- Generation based on MAC address
- Randomly

Structure based on EUI-64 :
- OUI 24bits
- inject FFFE
- Host ID (MAC address)

#### Link-local Unicast
Added auto with global address with `FE80/64`

## Multicast IPv6
- Mac address : `33:33:x:x:x:x` with `x:x:x:x` from last 4 bytes of IPv6 global address -> Can check multicast from ethernet
- `FF02::1:FFxx:xxxx` -> like IPv4 brodcast to all nodes (use by Route Announcement)
- `FF02::2:FFxx:xxxx` -> like IPv4 brodcast to all routers (use by Route Solicitation)
-  ...

### ICMPv6
ICMPv4 + ICMPv6 :
- Host confirmation
- Destination or Service Unreachable

ICMPv6 Router Discovery Protocol  + Neighbor Discovery Protocol :
- Router Solicitation (RS)
- Router Advertisement (RA)
- Neighbor Solicitation (NS)
- Neighbor Advertisement (NA)

Replace IPv4 ARP with :
- Request (Neighbor Solicitation)
- Answer (Neighbor Advertisement)

Use :
- Echo (ping)
- Traceroute
