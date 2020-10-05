Title: Change the hostname of a WLAN Pi
Authors: Nigel Bowden

# Change the hostname of a WLAN Pi

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


[<-- back][back]

<!-- Link list -->
[back]: index.md