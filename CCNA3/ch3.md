# CCNA3 - Chapter 3 -  EtherChannel
## Conception
- Physicaly different port but logicaly the same
- There is physical rendundancy
- Port channel : there is limitation of channel number and interface use, it depends on device.

Negociation :
- PAgP (Cisco) Protocol
  - desirable
  - auto
- LACP Protocol
  - actif
  - passive
- "on" : forced (no-negociation)

## Configuration
- Disable interface before configuring EtherChannel
- `show interface port-channel <channel#>`
- `show etherchannel summary`
- `show etherchannel port-channel` :
- `show interface etherchannel` : Interface's role in etherchannel

## Brief
