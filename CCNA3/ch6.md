# OSPF
## Multi OSPF
why multi-area ? All data are shared between routter in the same area

Area Roles :
Federated area -> area 0
Non federated area -> area !0

Router Roles :
- Internal router : inside 
- Backbone router : inside area 0
- ABR router : Between area
- ASBR Routers : Autonomous System Boundary Router) : connected to WAN

LSA types :
- 1 : Routeur LSA : Each routers in same zone exchange data
- 2 : Network LSA : Only DR can send it
- 3 : ABR routeur can send area informations
- 4 : ASBR Routeur can send inside information (default gateway informations -> WAN)
- 5 : ASBR Routeur can send external informations (Outside networks)

Routing table :
- O
- O IA
- O E1 | O E2
