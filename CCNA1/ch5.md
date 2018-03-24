# Chaptre 5


## Protocole Ethernet 2 (PDU = Trame)
>  Network access layer (modèle TCP/IP) (Ethernet Protocol)= phycsical layer + link layer (modèle OSI)

- Group 2 layers :
  - physique
  - couche liaison de données :
    - LLC (top sub-layer):
    - MAC (bottom sub-layer):
- La trame (frame) contains control sequence (CRC).

### MAC Sub-layer
- Implemented generaly by the network card
- Encapsulate data :
  - Add head and tail to the N-PDU (network PDU)
- Controle access :
  - Communicate directly with physical layer
  - Mutliple accès : Colision Detection (CSMA/CD) wired network (Ethernet) + Colision Avoidance (CSMA/CA) wireless network (wifi 802.11)

### LLC Sub-layer
- Manage communication between network and MAC sublayer

### Frame Ethernet
- IEEE 802.3 -> if lenght > 1500 => type for Ethernet
- Ethernet + IEEE 802.3 :
  - 64 octets min -> collision frame / Runt -> to detect colision (not use now)
  - 64 octets < frame lenght < 1518 octets (1500 data + 16 head/tail) => packet IP < 1500 octets (must fragment IP packet)

### Mac Adress
- 6 octets :
  - first part -> IEEE ID for company
  - second part -> ID for the component

- Adress Levels :
  - Physical adress : MAC
  - Logical Adress : IP
  - Process Adress : PORT
- Adress MAC Type :
  - Unicast : 1 destination (same LAN)
  - Broadcast : all destination
  - Multicast : Mutliple destination (first part : )

## Switch LAN
- Contain "MAC adress table" (link between port and mac adress)
- Switch (level 2) don't edit the frame format, do error control
- How Switch learn MAC Adress :
  - Clean at the beginning
  - Associate MAC adress to the port which recieved the frame
  - Broadcast frame if MAC adress unknown
  - Device X drop frame if the MAC Adress is not his.
- Foward modes :
  - "Store and Foward" -> check error
  - "Cut-through" :
    - "Fast-foward" : no need to wait the frame -> foward directly can't check error.
    - "Fragment-Free" : Can wait 64o to avoid collision.
- Buffer Memory :
  - Port Memory : FIFO (ex : the first frame is stored, the second frame recieved can't be fowarded before the first one)
  - Shared Memory
- Communication mode :
  - Duplex : can recieved and send at the same time
  - Half-Duplex
  - Auto : negociation between devices
- Auto-MDIX : know automaticaly -> cut-through and cross-over

## ARP (Address Resolution Protocol)
- Destination on same network : Use ARP Request (logical & between IP adress and network mask)
- Destination on other network : Need to use the gateway

- Can find ARP table : on gateway (router) or device (computer not switch)

- ARP request -> Broadcast (contains destination IP adress) | ARP answer -> Unicast (containes destination MAC adress)

- ARP poisening  
## Resume
