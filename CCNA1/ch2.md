# Chapter 2
## Objectifs
- Pro and Cons of static routing
- Config Cisco switch  ( ports , ...)
- Eyes on security attacs in commute environment
- Eyes on best practises

## Config commutateur
### Séquence d'amorcage de commutateur
1. POST
2. Execute bootloader
3. Init low level of processor
4. Init file system of flash memory
5. lacate + load in memory -> OS image

### Voyants LED
LED lights give informations (RTFM)

### Préparation gestion de commutateur de base
- Remote manage
- A IP @ and mask must be configured
- If managed remotly, must config gateway

### Fonction auto-MDIX
- Differentes copper wires (throughput and cross-over)
