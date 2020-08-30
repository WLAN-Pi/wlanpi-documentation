Title: Frequently Asked Questions
Authors: Nigel Bowden

# FAQ

## Where can I get the latest WLAN Pi image?

TBA - new process for V2.x.x

## How do I find which image version is currently installed on my WLAN?

If you look on the top-level "home" page of the front panel display, the version number of the image should be shown on the top left of the display.

If you see no version number, it may be that you have quite an old version of image. If you have network connectivity to the WLAN Pi, browse to it  (169.254.42.1 if you're on the USB OTG connection) and look at the bottom right of the web page to see the image version.

## How do I burn a WLAN Pi image?

If you'd like to burn a WLAN Pi image on to a kit you've bought or update the image of your existing WLAN Pi, here is a video explaining the process:

<iframe width="560" height="315" src="https://www.youtube.com/embed/sD4WlNyyWDs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## How do I change the password for the wlanpi user

Changing the default password for the wlanpi user is highly recommended to help secure your unit.

To change from the default password (which is 'wlanpi'), SSH to the WLANP Pi and use the 'passwd' command as follows:

```
wlanpi@wlanpi:~$ passwd
Changing password for wlanpi.
(current) UNIX password: wlanpi
Enter new UNIX password: <enter new pwd>
Retype new UNIX password: <enter new pwd again>
passwd: password updated successfully
wlanpi@wlanpi:~$
```

**If connecting the WLAN Pi to any network, changing the default password should be a top priority. If the WLAN Pi becomes compromised as default credentials have been left in place, this could have very serious consequences.**

## How do I change the hostname of my WLAN Pi

By default, the hostname of your WLAN Pi is : wlanpi

If you'd like to change this to a more meaningful hostname, then you will need to SSH to your WLAN Pi and update the ```/etc/hostname``` and ```/etc/hosts``` files, followed by a reboot of the WLAN Pi:

Edit the /etc/hostname file using the command:

```
 sudo nano /etc/hostname
```

There is a single line that says 'wlanpi'. Change this to your required hostname. Then hit Ctrl-X  and "y" to save your changes.

Alternatively, you may also use the following CLI command to achieve the same result:

```
sudo hostnamectl set-hostname <name>
```

Whichever method is used to update the hostname file, next edit the /etc/hosts file:

```
 sudo nano /etc/hosts
```
Change each instance of 'wlanpi' to the new hostname (there are usually two instances). Then hit Ctrl-X  and "y" to save your changes.

Finally, reboot your WLAN Pi:

```
 sudo reboot
```

## How do I set the timezone on my WLAN Pi?

From the CLI of your WLAN Pi:

```
sudo dpkg-reconfigure tzdata
```

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

TBA - New info pending for v2.x.x

## Where can I get help support with my WLAN Pi?

Support is on a volunteer/best efforts basis by project volunteers. Try [here][support]

## How do I suggest a new feature for the WLAN Pi?

If you have a feature suggestion for the WLAN Pi, please get along to the GitHub site for the project and open an issue ticket with your suggestion: [link][suggestions] (this will need a (free) GitHub account to create an issue)

<!-- Link list -->
[support]: /v1/support.md
[wlanpi_releases]: https://github.com/WLAN-Pi/wlanpi/releases
[burn_image]: https://youtu.be/sD4WlNyyWDs
[adapter_sheet]: https://docs.google.com/spreadsheets/d/1yAjO2vZuIfJ9BwI5cQ_qu72HpyEuETj4Zd7bWBnskDM/edit#gid=0
[suggestions]: https://github.com/WLAN-Pi/wlanpi/issues
[Win10_Host_Issue]: https://dutchwifigeek.blogspot.com/2019/10/using-wlan-pis-usb-host-interface-in.html

