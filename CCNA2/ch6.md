# CCNA2 - Chapter 6 - Static routing
## Implement static routing
- Static routes are not announced on only static managed LAN
- Take time to maintain
- Need to know all the LAN
## Config statics routes
- Type of statics routes in IPv4:
  - Next hope route
  - Static route directly connected
  - Static route entirely specified
- Type of statics routes in IPv4 :
  - Next hope route
  - Static route directly connected
  - Static route entirely specified : Set IPv6 prefix of next hop and output interface (cause same link local address can be multiple on the router with multiple LAN)

- Set default gateway :
  - IPv4 : `[no] ip route 0.0.0.0 0.0.0.0 <ip-address|exit-interface>`
  - IPv6 : `[no] ipv6 route ::/0 <ipv6-address|exit-interface>`

Routing protocol by class (sending routes without subnet mask) :
- Check if same network then check if same subnet mask, then send route
- Check if note same network then send route
## CIDR & VLSM
Use class wast addressing
CIDR Classless Inter-Domain Routing
### VLSM
Don't use VLSM with class routing protocol
Start segmentation by the bigest subnet and finish by the smallest
## Config recapitulatif and floating statics routes
### recapitulatif routes
Set common first bits of two subnet and add it to route table and delete old route

### Floating
Add routes with differents administrative distance
> ip route 0.0.0.0 0.0.0.0 172.16.2.2
ip route 0.0.0.0 0.0.0.0 10.10.10.2 5

`ip route <@ip> <subnet_mask> [metric]`

Sending recapitulatif route use less bandwidth than sending all routes

## Troubleshooting
## Resume
