Title: Profiler
Authors: Nigel Bowden

# Profiler

The profiler utility is used to determine the 802.11 capabilities of wireless clients. This information is invaluable when designing a wireless LAN, as client characteristics need to be fully understood for the design process.

It works by creating a "dummy AP" which broadcasts a test SSID. Clients that need to be profiled then attempt to associated with the test SSID. Although the clients cannot join the SSID, their association frames are captured and analyzed to reveal their characteristics. A textual report for each client is created and stored on the WLAN Pi - this may be accessed via the WLAN Pi web GUI.

A demonstration of using the profiler is shown in the video below by Jeff Nyman:

<iframe width="560" height="315" src="https://www.youtube.com/embed/SVjCwcrxUPU" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

You can go direct to the video on [YouTube][video_link] using this [link][video_link].

Visit the [profiler GitHub site][profiler_github] for more details.


<!-- Link list -->
[video_link]: https://youtu.be/SVjCwcrxUPU
[profiler_github]: https://github.com/WLAN-Pi/profiler


