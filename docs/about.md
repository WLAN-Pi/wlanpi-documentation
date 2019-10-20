# About
<div style="float: right;">
![WlanlPi Logo](images/wlanpi_v_small.png)
</div>
The WLAN Pi project started in 2016 at [WLPC][WLPC_2016]. The goal was to create a portable, ready-to-use device that could function as a network endpoint for measuring network performance and throughput.

Since then, it has been widely embraced in the awesome wireless community and after many contributions, this tiny box has evolved well beyond a network performance testing device. 

Today, it can also be used as a remote Wi-Fi scanner, packet capture tool, portable Wi-Fi signal generator and much more! These capabilities assist wireless professionals with designing better wireless networks, troubleshooting issues more quickly, and validating wireless network performance. 

## Hardware

There are two main component parts to the WLANPi: a NEO2 hardware platform and a wireless adapter. Other useful assessories are available, but these are the two must-have components to get yourself up and running with a WLANPi. See our [Getting Started][Getting_Started] page to find out how you can get your own WLANPi setup. 

### NEO2
<div style="float: right;">
![CF-912](images/neo2_bare.jpg)
</div>
At the heart of the WLAN Pi is the NanoPi NEO2, a super tiny quad-core single-board computer (SBC). The NanoPi NEO2 shares some similarities to the more well known Raspberry Pi, however the NanoPi is less than ½ its size, consumes less power, and it can push over 900 Mbps over its gigabit ethernet connection.

Specs:

- CPU: Allwinner H5, Quad-core 64-bit high-performance Cortex A53
- DDR3 RAM: 1GB
- Storage: microSD (16 GB card included), can be expanded up to 128GB

More info: <http://wiki.friendlyarm.com/wiki/index.php/NanoPi_NEO2>

### Wi-Fi Adapter
<div style="float: right;">
![CF-912](images/cf912.jpg)
</div>
The Wi-Fi adapter is a Comfast CF-912ac, Realtek rtl8812au chipset, one of the few 802.11ac chipsets that support monitor mode and packet injection in linux. 
Important Specs: Dual-band, 2x2:2, 802.11ac

[WLPC_2016]: https://www.wlanpros.com/resource/?wpv-category=2016-us-phoenix&wpv_aux_current_post_id=2623
[Getting_Started]: getting_started.md
