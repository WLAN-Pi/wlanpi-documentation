Title: V2.0.0 Announcement
Authors: Nigel Bowden

# V2.0.0 Announcement

# WLAN Pi v2.0.0
>WLAN Pi v2 includes some major changes behind the scenes, rebuilt from the ground up on [Armbian](https://www.armbian.com/) using the latest Linux kernel (5.8). This update also includes a revamped toolset, many usability improvements, and paves the way for the future of the project to support multiple hardware platforms.

Core contributors: @danielmundi @wifinigel @joshschmelzle @jiribrejcha @crvallance @adriangranados 

# Summary
* [New WebUI](#new-webui)
* [New Web Admin Interface](#new-web-admin-interface)
* [New Server Mode](#new-server-mode)
* [Updated Profiler](#updated-profiler)
* [Updated Front Panel Menu System (FPMS)](#updated-front-panel-menu-system)
* [Updated Wiperf Mode](#updated-wiperf-mode)
* [Updated Wi-Fi Drivers](#updated-wi-fi-drivers)

Documentation Site (WIP): [docs.wlanpi.com](https://wlan-pi.github.io/wlanpi-documentation/v2/)

---
>**Note 1:** The USB Ethernet IP address has been changed to use a static link-local address of **169.254.42.1**

>**Note 2:** Several previously included tools have been dropped from the WLAN Pi 2.0 toolset. This allowed us to refocus our efforts on improving a core set of tools that were determined to be the most used and useful.

More details on the toolset and whats changed can be found [here](https://docs.google.com/spreadsheets/d/1Uu-UXLg82gJyFlO7vpMPn8un5plKhiNx2cn6Vy4s48U/edit?usp=sharing).

---
### <a id="new-webui"></a> New WebUI
<img width="415" alt="image" src="https://user-images.githubusercontent.com/17500656/94476340-f6f5f080-0195-11eb-8aa4-02a1c7315e3c.png"></img>
* Extensible framework built on Flask
* Network information includes:
  * Reachability test
  * Local IP info
  * Public IP info
  * CDP and LLDP neighbor info
* Profiler results
* LibreSpeed test improved 

---
### <a id="new-web-admin-interface"></a> New Web Admin Interface
<img width="347" alt="image" src="https://user-images.githubusercontent.com/17500656/94484885-b3ee4a00-01a2-11eb-8d10-74faf8aa844e.png"></img>
- Cockpit Project - https://cockpit-project.org/ 
- Adjust time zone
- Manage services
- Monitor and administer multiple WLAN Pi’s at the same time
- Embedded terminal

---
### <a id="new-server-mode"></a> New Server Mode
<img width="134" alt="image" src="https://user-images.githubusercontent.com/17500656/94473825-594cf200-0192-11eb-9a96-696a67299d96.png"></img>
- Ideal for lab, provisioning, staging and software upgrades of network devices
- Enables all services on the WLAN Pi like DHCP server, TFTP server, Wi-Fi console, wireless access to the WLAN Pi and more coming soon
- Safety first: this mode is non-persistent and WLAN Pi will switch back to its default “Classic” mode after reboot
- Many use cases:
  - Build a lab network, demonstration or a Proof the Concept (PoC) setup
  - Software upgrade of a switch, controller or AP using the TFTP server
  - Point APs to their controller by configuring Option 43 on the WLAN Pi DHCP server http://bit.ly/wlanpi-option43
  - Easily convert hundreds of APs from Mobility Express or Embedded Wireless Controller mode to Lightweight mode https://bit.ly/convert-to-lightweight 

---
### <a id="updated-profiler"></a> Updated Profiler
<img width="301" alt="image" src="https://user-images.githubusercontent.com/17500656/94485433-88b82a80-01a3-11eb-8bf8-10316010fad8.png"></img>
- Complete rewrite of the codebase from python2 to python3
- Integrated and customized fakeap scapy code
- Improved performance
- Packaged and isolated in its own Python environment
- Dozens of minor improvements

---
### <a id="updated-front-panel-menu-system"></a> Updated Front Panel Menu System (FPMS)
<img width="425" alt="image" src="https://user-images.githubusercontent.com/17500656/94485884-362b3e00-01a4-11eb-8206-4ca0fdbafb8c.png"></img>
- Button clicks are 50% more responsive! No more double pressing buttons :)
- Button layout options - choose your preferred button layout
- CDP neighbour - now also shows software version if advertised
- Port blinker - identify switch port number on the far end of the Ethernet cable by blinking switch port LEDs
- Mist cloud test - verify connectivity to the cloud 

---
### <a id="updated-wiperf-mode"></a> Updated Wiperf mode
<img width="399" alt="image" src="https://user-images.githubusercontent.com/17500656/94473705-273b9000-0192-11eb-8d4c-4b6c13178777.png"></img>
* Support for testing over Ethernet
* Support for reporting in to Influx/Grafana
* Canned dashboard report improvements

More details: https://wifinigel.github.io/wiperf/

---
### <a id="updated-wi-fi-drivers"></a> Updated Wi-Fi Drivers
MediaTek MT7612U based Wi-Fi adapters are now fully supported.

![519zejg3wzL _AC_SL1350_2](https://user-images.githubusercontent.com/17500656/94504040-77841380-01cd-11eb-983a-ecf855e7b9be.jpg)   ![20181205173738esukh2](https://user-images.githubusercontent.com/17500656/94504141-bb771880-01cd-11eb-8cf1-1f31cdca8c33.jpg)   ![unnamed3](https://user-images.githubusercontent.com/17500656/94504398-4ce68a80-01ce-11eb-8333-bfda51d713d2.jpg)

Ex. Netgear A6210, Alfa AWUS036ACM, or any other Wi-Fi adapter that uses the MT7612U chipset.

