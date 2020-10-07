Title: Frequently Asked Questions
Authors: Nigel Bowden

# FAQ

## I hear the NEO2 is no longer available - when will replacement hardware be available?

The original WLAN Pi platform was based on the [NEO2 SBC Kit][Friendlyarm]{target=_blank} which was available from the Friendly Elec company in China. However, due to a lack of availability of some components for the board, they ceased production of the NEO2 board and hence the NEO2 kit. 

The NEO2 kit comprised the NEO2 board, an OLED display board, metal case and an SD card. Theoretically, if you can find a NEO2 board in some dusty corner of the Internet, you could still put together your own kit, as the remaining kit items are still available from Friendly Elec. 

It's also worth checking our [suppliers][suppliers] page to see if they have any kits available. They may occasionally obtain some surplus stock, if and when they can find it, so may have the NEO2 kit in stock in limited numbers from time to time.

To answer the question about replacement hardware, the honest answer is that there is no definite date for a replacement hardware platform being available. The team has recently looked at the new NEO3 board from Friendly Elec, but this has been discounted as a replacement at this time due to a number of technical limitations which ruled it out.

The team is currently investigating the "Rock Pi E" SBC as a possible replacement to the NEO2, though this will require an additional HAT to provide additional features that are required. Realistically, given the requirement for the fabrication of an additional HAT and items such as printed cases, the end of 2020 is probably a realistic time-frame for new hardware being available. As we move closer to finalising hardware details, we will be able to provide a more accurate timescale assessment - stay tuned! 


## Where can I get hold of a WLAN Pi kit?

Please check out our [suppliers page][suppliers] for the latest information on WLAN Pi hardware availability.

## Where can I get the latest WLAN Pi image?

You can obtain the latest base image from the releases area of the WLAN Pi GitHub repository:

[https://github.com/WLAN-Pi/releases/releases](https://github.com/WLAN-Pi/releases/releases){target=_blank}

Once downloaded, you can burn it on to an SD card as described in the following administration document: [Burning a WLAN Pi Image][burn_image]

## How do I find which image version is currently installed on my WLAN?

If you look on the top-level "home" page of the front panel display, the version number of the image should be shown on the top right of the display:
<div>![WLAN Pi Display](images/wlanpi_display.jpg)</div>

If you are the CLI of the WLAN Pi, you may also check by performing the following command:

```
wlanpi@wlanpi:/$ cat /etc/wlanpi-release
VERSION="2.0.0-dev3"
```

## How do I burn a WLAN Pi image?

Checkout this administration note: [Burning a WLAN Pi Image][burn_image]

## How do I change the password for the wlanpi user?

Checkout this administration note: [Change the Password of the wlanpi User][change_pwd]

**If connecting the WLAN Pi to any network, changing the default password should be a top priority. If the WLAN Pi becomes compromised as default credentials have been left in place, this could have very serious consequences.**


## How do I change the hostname of my WLAN Pi

Checkout this administration note: [Change the hostname of a WLAN Pi][hostname]


## How do I set the timezone on my WLAN Pi?

Checkout this administration note: [Change the Timezone of a WLAN Pi][timezone]


## How do I connect my WLAN Pi to my wireless network?

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

## I'm having difficult getting a connection over the USB link to my WLAN Pi? What's going on?

The WLAN Pi has a very useful feature that allows you to connect your Mac or Window machine to a WAN Pi via a USB connection. This is effectively an Ethernet over USB connection, also known as an OTG connection (On The Go).

This requires a USB to micro-USB cable to hook up your laptop/Mac to the micro-USB socket on the WLAN Pi (which is also used to power the WLAN Pi).

This is very cool as it both powers up your WLAN Pi and gives you a local network connection to the WLAN Pi so that you can SSH or browse in to it.

There are two main issues we have seen with connectivity over the OTG connection:

1. Some cables that look like an OTG cable (i.e. a regular USB plug on one end and a micro-USB on the other) are, in fact, just phone charger cables and only have the power wires through. This means there are no data wires and you can never establish the OTG connection. The WLAN Pi will power up, but the OTG connection will not work. (You can check if you have an OTG connection by looking at the network interfaces on your laptop/Mac - if OTG is working, a new Ethernet port automagically appears.) 
If you hit this issue, try another cable (or two)

2. The second issue we hear about impacts Windows users. Please check out this super blog post if you have a Windows laptop and you think your cable is good: [Blog Post Link][Win10_Host_Issue]

## Which wireless adapters are supported on the WLAN Pi ?

Please checkout our [Supported Hardware][supported_hardware] page.

## Where can I get help support with my WLAN Pi?

Support is on a volunteer/best efforts basis by project volunteers. Try [here][support]

## How do I suggest a new feature for the WLAN Pi?

If you have a feature suggestion for the WLAN Pi, please get along to the GitHub site for the project and open an issue ticket with your suggestion: [link][suggestions] (this will need a (free) GitHub account to create an issue)

<!-- Link list -->
[support]: support.md
[suppliers]: suppliers.md
[wlanpi_releases]: https://github.com/WLAN-Pi/wlanpi/releases
[burn_image]: https://youtu.be/sD4WlNyyWDs
[adapter_sheet]: https://docs.google.com/spreadsheets/d/1yAjO2vZuIfJ9BwI5cQ_qu72HpyEuETj4Zd7bWBnskDM/edit#gid=0
[suggestions]: https://github.com/WLAN-Pi/wlanpi/issues
[Win10_Host_Issue]: https://dutchwifigeek.blogspot.com/2019/10/using-wlan-pis-usb-host-interface-in.html
[burn_image]: admin/burn_image.md
[hostname]: admin/hostname.md
[change_pwd]: admin/change_pwd.md
[timezone]: admin/timezone.md
[Friendlyarm]: https://www.friendlyarm.com/index.php?route=product/product&product_id=189
[supported_hardware]: supported_hardware.md#wireless-adapters
