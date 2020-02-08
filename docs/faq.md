Title: Frequently Asked Questions
Authors: Nigel Bowden

# FAQ

## Where can I get the latest WLAN Pi image?

The latest WLAN Pi image is available [here][wlanpi_releases]

(avoid the alpha releases, they are unstable, development builds, Beta are usually pretty good but may have the odd bug)

## How do I find which image version is currently installed on my WLAN?

If you look on the top-level "home" page of the front panel display, the version number of the image should be shown on the top left of the display.

If you see no version number, it may be that you have quite an old verison of image. If you have network connectivity to the WLAN Pi, browse to it  (192.168.42.1 if you're on the USB OTG connection) and look at the top of the web page to see the image version.

## How do I burn a WLAN Pi image?

If you'd like to burn a WLAN Pi image on to a kit you've bought or update the image of your existing WLAN Pi, here is a video explaining the process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/sD4WlNyyWDs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## How do I change the hostname of my WLAN Pi

By default, the hostname of your WLAN Pi is : wlanpi

If you'd like to change this to a more meaningful hostname, then you will need to SSH to your WLAN Pi and update the ```/etc/hostname``` and ```/etc/hosts``` files, followed by a reboot of the WLAN Pi:

Edit the /etc/hostname file using the command:

```
 sudo nano /etc/hostname
```

There is a single line that says 'wlanpi'. Change this to your required hostname. Then hit Ctrl-X  and "y" to save your changes.

Next, edit the /etc/hosts file:

```
 sudo nano /etc/hosts
```
Change each instance of 'wlanpi' to the new hostname (there are usually two instances). Then hit Ctrl-X  and "y" to save your changes.

Finally, reboot your WLAN Pi:

```
 sudo reboot
```

## Where can I get help support with my WLAN Pi?

Support is on a volunteer/best efforts basis by project volunteers. Try [here][support]

## How do I set the timezone on my WLAN Pi?

From the CLI of your WLAN Pi:

```
sudo dpkg-reconfigure tzdata
```

## How do I connect my WLAN Pi to my wireless network?

Assuming your network uses a PSK, simply edit the follwing files:

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
Enter your SSID and PSK in the areas indicated in the file. 

Finally, unplug and replace your USB wireless NIC, or reset your WLAN Pi for the new settings to tke effect.

(For other security methods, look in the following file for configuration examples: /home/wlanpi/wiperf/conf/etc/wpa_supplicant/wpa_supplicant.conf)

<!-- Link list -->
[support]: support.md
[wlanpi_releases]: https://github.com/WLAN-Pi/wlanpi/releases
[burn_image]: https://youtu.be/sD4WlNyyWDs

<small><br><i>Page last updated: {{ git_revision_date }} </i></small>