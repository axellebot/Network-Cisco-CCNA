# OSPF - Adjust and troubleshoot single area OSPF
## Advanced configuration - Single Area OSPF

OSPF Network :
- Point To Point
- Multi-access (Ethernet)
- NBMA Access (Frame-relay)
- Point-to-multipoint (Hub and spoke)
- Virtual Links

Designated Router (DR) :
- Receiving all information
- Foward to others (Multicast)
- If it crashed use BDR
- If re-up became DROthers

BDR (Backbone Designated Router) :
- If needed it become DR

DROthers
- Elect DR and BDR if needed
- Send information to BDR

Know role :
`show ip ospf interface`
Router :
- Can be DR, BDR or DROthers in multiple network
- Only 1 BR and BDR in 1 network

Links :
- FULL/DROTHER : Connected to a DROTHER
- FULL/DR : Connected to the DR
- FULL/BDR : Connected to the BDR
- 2-WAY/DROTHER : Me and my neoghbor are DROTHER

Designation process :
- Interface priority :
  - First (Lowest) -> BR
  - Second (Highest)-> BDR
- Routeur ID :
  - Highest : BR
  - Second highest : BDR

`ipv6 ospf priority <#>`

Hello/Dead Intervals must be the same beetween routers.
`ip ospf hello-interval`
`ip ospf dead-interval`

Authentication : Signature verification with symetrical key

`ip ospf message-digest-key <key>` : md5 password
`area <area-id> authentication message-digest` : en mode configuration router
`area <area-id> authentication message-digest`

## Troubleshoot OSPF
Problemes :
- Interfaces are not on the same network
- OSPF network type -> area different
- Hello/Dead intervals are differents
- Interfaces are configured as passive
- `network` OSPF command missing
- Authentication not configured

Steps :
- Check neighbor table `ip ospf neighbor`
