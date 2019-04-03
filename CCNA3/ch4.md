# CCNA3 - Chapter 4 - WLAN
## Introdduction
- Describe wireless technologies and standards
- Describe WLAN components
- Describe wireless topology
- Describe 802.11 structure
- Describe channel management
- Describe security mecanism for WLAN
- Configure wireless connection between client and hotspot
- Fix wireless configuration problems

## Concepts
Advantages :
- Flexibility
- More productivity
- Best cost consumption
- Scalability

Categories :
- WPAN Wireless Personnal Area Network (Bluetooth)
- WLAN Wireless LAN 802.11
- WMAN Wireless Metropol Area Network (working like mobile network)

Wireless Technologies :
- Bluetooth IEEE 802.15
- Wi-Fi IEEE 802.11
- WiMAX (Worldwide Interoperability for Microwave Access)
- Cellular broadband
- Satellite broadband

Radio Frequency :
- International responsibility : ITU-R
- 2,4 GHz (UHF) - 802.11b/g/n/ad
- 5 GHz (SHF) - 802.11a/n/ac/ad
- 60 GHz (EHF) - 802.11ad

Certifications Wifi Alliance :
- Wifi certified
- Wifi certified with variant
- Wifi Protect Setup
- Wifi Direct

Wireless peripheric :
- NICs
- AP

Domestic Wireless Router :
- Used as :
  - Hotspot : 802.11
  - Switch
  - Router : gateway
  - Modem (for ADSL and fiber)

Professional Wireless solution :
- Hotspot :
  - Autonomous : configured with CLI
  - With controller : configured by server
  - Clustered : grouped configuration

Deployment on big size :
- Virtual Machine
- Controller
- Router module
-  Cloud Cisco Meraki

Antenna :
- Omnidirectionnelles
- Dirictionnel
- Yagi

Topologies Wifi 802.11 :
- Ad-hoc : IBSS (service)
- Infrastructure  :
  - BSS : 1 SSID - 1 hotspot
  - BSA : area of BSS
  - ESS : 1 SSID many hotspot
  - ESA : all BSA

## Operation

Frame :
- Header :
- Frame control : type of frame
  - 0x0. Gestion :
    - 0x01
    - 0x0. : authentication
    - 0x08 Beacon frame : announce SSID
  - 0x1. Control :
    - 0x1B Trame DPE- > RTS Request To Send
    - 0x1C Trame PAE  ->  CTS Clear To Send
    - 0x1D Trame ACK  ->
  - 0x.2. Data :

Type of  Frame :
- Manage :
- Detection
- Authentication
- Association
- Control
- Data

Association parameters :
- SSID
- Password
- Network mode
- Security mode
- Channel settings

Hotspot Detection :
- Passive mode : the hotspot broadcast SSID
- Actif mode :
- SSID is hidden by hotspot
- Client seek knew hotspot on all channels

Hostpost Authentication :
- Open : No Authentication
- Shared keys (with PSK)
- Auth Server

Hostpost Association : Receiving BSSID (MAC)

Channels saturation :
- DSSS
- FHSS (Frequency-Hopping Spread)
- OFDM (Orthogonal Frenquency-Division Multiplexing)  

## Security
- Wireless intrusion
- Not desirable hotspot
- DOS

Attacks :
- spoofed disconnect attack
- CTS flood
- man in the middle

Conter :
- hide SSID
- MAC mask

- WEP : RC4 encryption + CRC-32 integrity
- WPA : TKIP encryption + MIC intergrity
- WPA2 :

IEEE 802.11i, WPA & WPA2 use those encryption :
- AES Advanced Envryption Standard
- TKIP

Mode :
- Personal : shared key
- Enterprise :
  - EAP + RADIUS (Remote Authentication Dial-in User Service)
  - CAS
  
## Configuration

## Resume
