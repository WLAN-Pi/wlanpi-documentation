Title: Connecting You WLAN Pi to a Wireless Network
Authors: Nigel Bowden

# Connecting You WLAN Pi to a Wireless Network

Assuming your network uses a PSK, simply edit the following files:

- /etc/network/interfaces
- /etc/wpa_supplicant/wpa_supplicant.conf


### /etc/network/interfaces 

Edit the file as follows:

```
sudo nano /etc/network/interfaces
```

Edit the following section of the file for wlan0:

```
# Wireless adapter #1
# Armbian ships with network-manager installed by default. To save you time
# and hassles consider using 'sudo nmtui' instead of configuring Wi-Fi settings
# manually. The below lines are only meant as an example how configuration could
# be done in an anachronistic way:
#
allow-hotplug wlan0
iface wlan0 inet dhcp
#address 192.168.0.100
#netmask 255.255.255.0
#gateway 192.168.0.1
#dns-nameservers 8.8.8.8 8.8.4.4
#   wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
# Disable power saving on compatible chipsets (prevents SSH/connection dropouts over WiFi)
wireless-mode Monitor
#wireless-power off
```

Remove the "#" character from the start of the line:

```
#   wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
```

Save the file by hitting CTRL-x

### /etc/wpa_supplicant/wpa_supplicant.conf

Edit the file as follows:

```
sudo nano /etc/wpa_supplicant/wpa_supplicant.conf
<make your changes>
CTRL-x
```
Enter your SSID and PSK in the areas indicated in the file. For the new settings to take effect, you have 3 options:

* Unplug and re-insert your USB wireless NIC
* Issue the following command on the WLAN Pi CLI : ```sudo ifdown wlan0; sudo ifup wlan0```
* Reboot your WLAN Pi (remove the power or issue the ```sudo reboot``` command on the CLI) 

(For other security methods, look in the following file for configuration examples: /home/wlanpi/wiperf/conf/etc/wpa_supplicant/wpa_supplicant.conf)



[<-- back][back]

<!-- Link list -->
[back]: index.md