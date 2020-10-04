# CCNA4 - Chapter 8 - Troubleshooting

## Troubleshooting strategy

### Documentation
Documentation for troubleshooting:
- Configuration
- physicaly (devices ...) and logicaly
- "baseline"

Device information:
- Localization
- IOS images
- Host

End device information:
- IPv4 and IPv6 address
- Mask address
- gateway address

Topology information:
- physicaly
- logicaly

### Baseline

Baseline of the network:
- Initial monitoring
- Non-schedule monitoring
- See (ab)normal performance
- Type of communication
- know baseline period

### Measuring trafic

Use all cisco `show` commands

### Work-Flow
- Gathering symptoms (End user)
- Identifying trouble (bottom-up or top-down or divide and conquer the TCP/IP model )
- Create solution and implement it
- Add issue to documentation

## Scenes

### IP SLA
Metrologie active OR helper to fix troubleshoots
- Delay
- jitter
- Packet loss

`ip sla <op#>`
`show ip sla application`

```
Router(config-ip-sla)# icmp-echo {dest-ip-address|dest-hostname} [source ip {ip-address|hostname} | source-interface id-interface]
```

```
Router(config)# ip sla schedule <operation#> [life {forever | <secs>}] [start-time {hh:mm[:ss] | pending | now | after hh:mm:ss] [ageout <secs>] [recuring]
```

### Tools

- NMS (Network Management) (ex: HPOV, SolorWind)
- Protocol Analyzer (ex: Wireshark)
- Devices (ex: Wire tester)
- Syslog server (Urgent (0) -> OK (7))
