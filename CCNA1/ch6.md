# Chapter 6
## Introduction

## Network Layers Protocols
- Contains Logical address (ex : IP @)
- Encapsulate Transport PDU (Segment) -> become SDU
- IP :
  - Without connection
  - Best Effort -> No control
  - Independant from the support -> wired or wireless ...
- IPV4
  - Headers :
    - Version (4bits)
    - Internet Header Lenght (4bits)
    - DS Differencial Services (16bits) (old TOS) -> priority
    - Total lenght
    - Identification (ID of fragment)
    - Flag + Fragment Offset
    - TTL (8bits)
    - Protocoles (8bits)
    - Header Checksum
    - Source IP @ (32bits)
    - Destination IP @ (32bits)
    - Data
- why IPV4 to IPV6 ? :
  - Lack of IPV4 address
  - Missing P2P connectivity
- IPV6 :
  - Bigger addressing
  - Less field
  - No NAT needed (all have IPV6)
  - Advantage :
    - Header simplified
    - More Usefull data -> better throug-put and efficient transporatation
  - Headers :
    - Version
    - TOS
    - Flag (ex: for load balancing)
    - Used Data Lenghts
    - Next header
    - TTL
    - Source IP @
    - Destination IP @

## Routing
- Default gateway :
  - Routing to another network
  - Receive and Send data
- Populate route table :
  - Interface = 1 subnet = 1 route -> letter C in routing table
  - Learn by routing protocols : - > different in routing table (ex: EIGRP /RIP /OSPF)
  - Manualy -> Statique S in routing table  
- Routing table datas type :
  - Identify the how we learn the Network (S Static, D Dynamic)
  - Identify the destination
  - Identify the fiability (Directly connected/ Static / other protocol )
  - Identify the metric to reach the remote network
  - Identify the ip address of the next jump
  - Identify the age of the route
  - Identify the output interface

## Routers
- Anatomy :
  - CPU
  - Memory :
    - RAM : Runnong config
    - NVRAM : Startup config
    - Flash : IOS
    - ROM : POST (Power On Self Test) + Boostrap (where to pull IOS Flash or network ?) + IOS limited
- Connections :
  - EHWIC Slots
  - Flash Slots
  - AUX port
  - LAN interface
  - Console RJ45
- Interfaces LAN + WAN (must be configured to remotly config)
    - Data : LAN RJ45 + WAN serie (extra bounds)
    - Manage : AUX + Console (intra bound)

- Boostrap :
  - load iOS from ROM in RAM
  - load configuration from SFTP or NVRAM or in RAM
  - `show version`-> show storage data and physical link data


## Cisco router configuration

## Resume
