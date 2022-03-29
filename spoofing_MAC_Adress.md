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
