Title: How to get started with the WLAN Pi
Authors: Nigel Bowden

# Getting Started with the WLAN Pi

## Building Your Own Kit
Rolling your own WLAN Pi takes a little more work than a pre-built kit, but with a little effort, you can source all of the parts and put one together.

Here is a list of the items you are going to need to source to build your own WLAN Pi:

- A NanoPi NEO2 from the [FriendlyArm company][Friendlyarm] (located in China): this is the WLAN Pi hardware platform itself (Note that this comes with a micro-SD card, so you do not need to purchase a separate card unless you want a [spare][Micro_SD])
- A Comfast CF-912 USB wireless adapter: this is the currently recommended adapter to support the various wireless operations that the WLAN Pi supports (you can usually get these fom eBay or [Amazon][CF912])
- An micro-SD to USB adapter module to allow images to be burned on to the WLAN Pi (easily sourced fom [Amazon][SD_Adapter])
- A USB to micro-USB cable to power and/or provide connectivity to the WLAN Pi (the flavour of USB cable will depend on your requirements)
 

Optional extra items:

- A [power supply][Power_Supply]. The Raspberry Pi PSUs work fine with the WLAN Pi and are readily available from [Amazon][Power_Supply] (Note that you can also use your USB to micro USB cable with a phone charger PSU in many cases if you'd prefer not to buy a dedicated PSU)
- [POE Splitter][POE_Splitter]. If you'd like to power your WLAN Pi from a switch POE port, a splitter is just what you need. However, ensure that you buy a [splitter that supports Gigabit-Ethernet][POE_Splitter], as many low-cost POE splitters are only 100mbps Ethernet (which is not great when you are using the WLAN Pi for speedtests or iperf). 
- Lithium battery (in case you want to leave the WLAN Pi powered on for a few hours somewhere)
- Extra [micro-SD card][Micro_SD] (in case you'd like a spare for different image versions or customizations)
- [Custom Handheld Case][Handheld_Case]: Designed specifically for use with the WLAN Pi, houses the Wi-Fi adapter and USB-C cable, while still exposing the USB port and ethernet port on the bottom, while still allowing access to the MicroSD slot - a great additon to make the WLAN Pi in to a true hnd-held tester! (Created by Joel Crane [@Potato_Fi][Potato_Fi] 
![Custom WLAN Pi case](images/wlanpi_case.jpg)

More info: <http://www.potatofi.com/2019/10/the-wlan-pi-handheld-case.html>


<!-- Link list -->
[Suppliers]: suppliers.md
[Friendlyarm]: https://www.friendlyarm.com/index.php?route=product/product&product_id=276
[WLPC_Store]: http://www.wlanpros.com/product-category/store/
[Potato_Fi]: https://twitter.com/Potato_Fi
[CF912]: https://amzn.to/2R9niFs
[SD_Adapter]: https://amzn.to/37aXoGO
[Micro_SD]: https://amzn.to/3ashgas
[Handheld_Case]: https://www.wlanpros.com/shop/wlan-pi-handheld-case-kit/
[Power_Supply]: https://amzn.to/2RzKVG2
[POE_Splitter]: https://amzn.to/2THvK0j

<small><br><i>Page last updated: {{ git_revision_date }} </i></small>