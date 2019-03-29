# Chapter 8 - EIGRP Configuration and troubleshooting
## Route Summary
Work with classfull -> bad : announcing all network of class X
`[no] auto-summary`

Add route to X via NULL to avoid loop
`ip summary-address eigrp 1 192.168.0.0 255.255.252.0`

EIGRP bandwith use have to be limited (default 50%) :
`<ip|ipv6> bandwith-percent eigrp <as-number-percent>`
`ip hello-interval eigrp <autonomous-system-ID> <time>`
`ip hold-time interval eigrp <autonomous-system-ID> <time>`

Loadbalancing with egal path:
`maximum-path <value>`

## Authentication
Create key :
```
key chain <name_of_key_chain>
key <key_id>
key-string <key_string_text>
```

Use the key :
```
ip authentication mode eigrp <automous-system-ID> md5
ip authentication key-chain eigrp <automous-system-ID> <name_of_key_chain>
ip authentication key
```
