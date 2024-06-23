---
layout: post
title:  "Homeassistant - A Life360 alternative"
date:   2024-01-21 09:18:00 +0200
categories: homeassistant
description: Use Homeassistants built-in location services as a Life360 alternative for device tracking and presence detection
tags: ["home automation", "tips"]
ShowToc: false
draft: false
---

Ever since the unofficial Life360 plugin for Homeassistant started to act spotty (API changes related to Cloudfare all the time that were no longer fun to try to keep up with) I have been looking for an alternative. 

Luckily the only thing I need to know is whether 1 or more person is `home` vs `not_home`. This I determine with a probably way too complex Node-RED if-this-then-that type of flow. As Homeassistant has this built-in it was actually quite easy to setup. There are a couple other services out there as well, but for some reason I trust Homeassistant more (than Life360, for sure) when it comes to sharing my data with a 3rd party...

![node_red_flow](/images/node_red_flow.png)

Steps to take:
* Remove all device_tracker related plugins first.
* Install the Homeassistant app on your iOS/Android device and setup it to allow Location Permission to `Always`. Set Location Accuracy to `Full` and Background Refresh to `Enabled`.
* For the `home` vs `not_home` logic you can use the device_tracker or check whether the device is connected to the wifi-network with the ssid sensor
* Update the Node-RED to make sure to use the proper Entity ID, e.g. `device_tracker.iphone_van_marcella_15_pro`

_UPDATE: I have been using this method for a couple months now and have had zero issues. I can't believe I wasted all this time trying to fix the Life360 plugin... This works straight out of the box if you need simple device tracking & location detection._
