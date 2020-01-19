Title: Frequently Asked Questions
Authors: Nigel Bowden

# FAQ

## Where can I get the latest WLAN Pi image?

The latest WLAN Pi image is available [here][wlanpi_releases]

(avoid the alpha releases, they are unstable, development builds, Beta are usually pretty good but may have the odd bug)

## How do I burn a WLAN Pi image?

If you'd like to burn a WLAN Pi image on to a kit you've bought or update the image of your existing WLAN Pi, here is a video explaining th eprocess: [burn_image][video]

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
change each instance of 'wlanpi' to the new hostname (there are usually two instances). Then hit Ctrl-X  and "y" to save your changes.

Finally, reboot your WLAN Pi:

```
 sudo reboot
```

## Where can I get help support with my WLAN Pi?

Support is on a volunteer/best efforts basis by project volunteers. Try [here][support]

### How do I set the timezone on my WLAN Pi?

From the CLI of your WLAN Pi:

```
sudo dpkg-reconfigure tzdata
```

<!-- Link list -->
[support]: support.md
[wlanpi_releases]: https://github.com/WLAN-Pi/wlanpi/releases
[burn_image]: https://youtu.be/sD4WlNyyWDs

<small><br><i>Page last updated: {{ git_revision_date }} </i></small>