Title: Frequently Asked Questions
Authors: Nigel Bowden

# FAQ

## Where can I get the latest WLANPi image?

The latest WLANPi image is available [here][wlanpi_releases]

(avoid the alpha releases, they are unstable, development builds, Beta are usually pretty good but may have the odd bug)

## How do I burn a WLAN Pi image?

If you'd like to burn a WLAN Pi image on to a kit you've bought or update the image of your existing WLAN Pi, here is a video explaining th eprocess: [burn_image][video]

<iframe width="560" height="315" src="https://www.youtube.com/embed/sD4WlNyyWDs" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## Where can I get help support with my WLANPi?

Support is on a volunteer/best efforts basis by project volunteers. Try [here][support]

### How do I set the timezone on my WLANPi?

From the CLI of your WLAN Pi:

```
sudo dpkg-reconfigure tzdata
```

<!-- Link list -->
[support]: support.md
[wlanpi_releases]: https://github.com/WLAN-Pi/wlanpi/releases
[burn_image]: https://youtu.be/sD4WlNyyWDs

<small><br><i>Page last updated: {{ git_revision_date }} </i></small>