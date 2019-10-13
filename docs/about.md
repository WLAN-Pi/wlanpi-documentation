# About
<div style="float: right;">
![WlanlPi Logo](images/wlanpi_v_small.png)
</div>
The WLAN Pi project started in 2016 at [WLPC][WLPC_2016]. The goal was to create a portable, ready-to-use device that could function as a network endpoint for measuring network performance and throughput.

Since then, it has been widely embraced in the awesome wireless community and after many contributions, this tiny box has evolved well beyond a network performance testing device. 

Today, it can also be used as a remote Wi-Fi scanner, packet capture tool, portable Wi-Fi signal generator and much more! These capabilities assist wireless professionals with designing better wireless networks, troubleshooting issues more quickly, and validating wireless network performance. 

## Hardware
### CPU
At the heart of the WLAN Pi is the NanoPi NEO2, a super tiny quad-core single-board computer (SBC). The NanoPi NEO2 shares some similarities to the more well known Raspberry Pi, however the NanoPi is less than ½ its size, consumes less power, and it can push over 900 Mbps over its gigabit ethernet connection.

Specs:

- CPU: Allwinner H5, Quad-core 64-bit high-performance Cortex A53
- DDR3 RAM: 1GB
- Storage: microSD (16 GB card included), can be expanded up to 128GB

More info: <http://wiki.friendlyarm.com/wiki/index.php/NanoPi_NEO2>

### Wi-Fi Adapter
The Wi-Fi adapter is a Comfast CF-912ac, Realtek rtl8812au chipset, one of the few 802.11ac chipsets that support monitor mode and packet injection in linux. 
Important Specs: Dual-band, 2x2:2, 802.11ac

### Custom Handheld Case
Designed specifically for use with the WLAN Pi, houses the Wi-Fi adapter and USB-C cable, while still exposing the USB port and ethernet port on the bottom, while still allowing access to the MicroSD slot. Creation of Joel Crane [@Potato_Fi][Potato_Fi] 
![Custom WLANPi case](images/wlanpi_case.jpg)

More info: <http://www.potatofi.com/2019/10/the-wlan-pi-handheld-case.html>


[WLPC_2016]: https://www.wlanpros.com/resource/?wpv-category=2016-us-phoenix&wpv_aux_current_post_id=2623
[Potato_Fi]: https://twitter.com/Potato_Fi