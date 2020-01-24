Title: Hotspot Mode
Authors: Nigel Bowden

# Hotspot Mode

Hotspot mode allows the WLAN Pi to become a small-scale AP to allow a variety of tests to be performed. 

It broadcasts an SSID, allowing the WLAN Pi to be used as a source for wall attenuation measurements ( see [this article][wall-measurements] ).

It may also be used to associate a client and perform speedtest measurements using the WLAN Pi's speedtest and iperf capabilities.

Finally, it also supports forwarding so that the WLAN Pi may also be connected to an Ethernet port while in hotspot mode and allow a wireless client to connect through to wired network.

To access hotspot mode, on the WLAN Pi front panel, select : Menu > Mode > Hotspot
<div style="float: center;">
![HotSpot](images/hotspot.jpg)
</div>
## References:

- [GitHub site][github]
- [WLAN Pi - Setup a Wi-Fi Hotspot (blog)][semifo-post]
- [WLAN Pi - Bridge Wi-Fi Hotspot to Ethernet Interface][semifo-eth]

<!-- Link list -->
[wall-measurements]: https://www.ekahau.com/blog/2015/09/07/wi-fi-planning-walls-and-dbs-measuring-obstruction-losses-for-wlan-predictive-modelling/
[github]: https://github.com/WLAN-Pi/wlanpihotspot
[semifo-post]: https://www.semfionetworks.com/blog/wlan-pi-setup-a-wi-fi-hotspot
[semifo-eth]: https://www.semfionetworks.com/blog/wlan-pi-bridge-wi-fi-hotspot-to-ethernet-interface


<small><br><i>Page last updated: {{ git_revision_date }} </i></small>