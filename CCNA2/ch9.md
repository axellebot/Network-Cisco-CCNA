# CCNA2 - Chapter 9 -  ACL (Access List)
## Caracteristics
Use ACL after routing.
Steps :
  - Check route
  - Check if ACL on interface if no ACL, send.
  - Check ACL entrance, match with ACE : apply deny or premit
  - no match implicit deny

Create 1 access-list for inbound and 1 for outband.

Implicit deny -> `deny any` if no match -> need 1 perm
Using wildcard mask in IPv4
- Filtering packet with protocl from network and transport

- ACL contains ACE (Access Entrance)

- ACL IDs :
  - Numbers :
    - 1 -> 99 + 1300>1990 : All Standard ACL for IP
    - 100 -> 199 + 2000-> 2669 : All extendes ACL for IP
  - Alphanumeric:
    - use CAPS
    - don't use space

- IP : 192.168.1.1 + Wildcard : 0.0.0.0 => filtering for host -> use `host <host_ip>`
- IP : 192.168.1.1 + Wildcard : 255.255.255.255 => filtering all -> use `any`

- 3 P rule :
  - 1 ACL by network protocol (ex: IPv4, IPv6)
  - 1 ACL by interface
  - 1 ACL by direction (in/out)

- Best Practices :
  - Writing ACL
    - write hosts
    - write network
  -
  -
  -

- Set ACL on interface :`ip access-group {access-list-number|access-list-name} {in|out}`
- Delete : `no access-list <access-list-number>`
- Add remark : `access-list <access-list-number> remark <remark>`

- Edit named ACL  : `ip access-list {standard | extended} <name>`

- Delete ACL line :
  ```
  ip access-list {standard | extended} <ACL_id>
  no <line_number>
  ```
- Insert ACL line :
  ```
  ip access-list {standard|extended} <ACL_id>
  <line_number> ...
  ```

- `show access-lists` : Show access-lists info and statistics
- `clear access-list counters <ACL_id>` reset counters

- Set access list on VTY :
  ```
  transport input ssh
  access-class <access_list_id> {in|out}`
  ```

## Standar IPv4 ACL
Close to destination (Filtering source address)
Config from config mode :

- Reorder ACE host to network

- Numerated :
  ```
  access-list <access-list-number> {permit|deny} [remark] {host <sender_address> | <sender_address> [sender_wildcard_mask] <sender_address> | any}  
  ```


## Extended IPv4 ACL
Close to sender (Filtering source,destination, source port and destination port)
Config from config mode :
```
access-list <access-list-number> {permit|deny} [remark] <protocol> {host <source_ip> | any | <source_network_ip> <wildcard_mask} [{eq|lt|gt} <source_port>] [dest_port {eq|lt|gt} <dest_port>] [etablished]
```
- Don't reorder ACE host to network

## Troobleshooting ACLs
- Switch source port and destination port
- wrong destination ip

## IPv6 ACLs

- Only nammed ACL
- Working as extended ACL

Differences :
  - `ipv6 traffic-filter` : Set on interface
  - No wildcard mask but prefix length
  - ICMPv6 (use like IPv4 ARP) :
    - `permit icmp any nd-na`
    - `permit icmp any nd-ns`

```
ipv6 access-list <access-list-name>
{deny|permit|remark} <protocol> {<source-ipv6-prefix/prefix-length> | any | host <source-ipv6-address>} [{eq | gt | ls} <source-port>]
```

## Brief
