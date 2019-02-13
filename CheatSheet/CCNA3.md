# Cheatography - CCNA3

## Spanning Tree
- Toggle ST : `[no] spanning-tree`
  - Edit link cost : `[no] spanning-tree cost <value>`
  - Edit mode `spanning-tree mode {rapid-pvst|pvst}`
- `show spanning-tree` : show spanning tree protocols info

## EtherChannel
- Set EtherChannel group : `[no] channel-group <group#> mode {active|auto|desirable|on|passive}>`
  - Force EtherChannel : `[no] channel-group <group#> mode on`
  - EtherChannel negociation with PAgP : `[no] channel-group <group#> mode {auto|desirable}`
  - EtherChannel negociation with LACP : `[no] channel-group <group#> mode {active|passive}`

- Change prompt to channel `interface port-channel <number>`

- Disable interface before configuring EtherChannel
- `show interface port-channel <channel#>`
- `show etherchannel summary`
- `show etherchannel port-channel` :
- `show interface etherchannel` : Interface's role in etherchannel
