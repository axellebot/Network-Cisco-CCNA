# CCNA4 - Chapter 2 - Point to Point connection

## Brief PPP
Serial instead of Parallel to avoid desynchronisation due to distance.
Use on interface :
- HSSI
- Sync interface
- Non-sync interface (ATM)

## PPP
PPP => LCP + x NCP (IPCP, IPv6CP)
Terminate LCP -> Terminate all NCP
Terminate NCP -> Terminate NCP

## Practice PPP
- Configure PPP :
```
interface s0/0/0
encapsulation ppp
```
- Compression :
```
interface s0/0/0
compress {predictor|stac}
```

- Quality: stop link under ratio
```
ppp quality <percentage>
```


- Multi-link
```
interface multilink <#>
ppp multilink
ppp multilink group 1

interface s0/0/0
ppp multilink
ppp multilink group 1
```

- Brief multilink
```
show ppp multilink
```

- Authentication :
```
ppp authentication {chap | chap pap | pap chap | pap}
```



PAP: Different or same password
CHAP : Same password

## Troubleshooting
