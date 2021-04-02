---
layout: post
title:  "Upgrade Unifi Controller to 6.x"
date:   2021-04-02 08:51:22 +0200
categories: update
description: Be aware of what you lose before you upgrade to 6.x
tags: ["unifi", "tips"]
ShowToc: false
draft: false
---

First I was a [bit hesitant](/blog/downgrade_unifi_controller/) on upgrading to 6.x as 5.14 was working absolutely fine. And why fix it if it ain't broken... 🤷‍♂️

Then the Hook Up came out with an [updated 3-part guide](https://www.youtube.com/watch?v=ufJ3dPAgFiM) on how to setup and configure the Unifi network and I made the adjustments to move away from the WLAN overrides. I have to say I am not completely happy yet with the controller's stability as it's disconnecting quite a bit. _To be clear: network- & performance-wise there are no issues at all. It's just the controller that drops offline significantly more often than before._

### On to the manual update:

First make sure you download a copy of the controller backup. Do so by going to [https://localhost:8443/manage/site/default/v2/settings/system/maintenance](https://localhost:8443/manage/site/default/v2/settings/system/maintenance)

SSH into your controller
```ssh {user}@{controller-ip}``` and enter your password.

Then enter the following commands one by one (no worries, your internet will keep working as we are only touching the controller)

Run ```sudo apt-get update && sudo apt-get upgrade -y```

It will ask you to back up first: you should. You can follow the steps on the screen.

If you get an error you can try:

```sudo apt update --allow-releaseinfo-change```

Let the update finish and then visit the controller via https://localhost:8443 or https://{controller-ip}:8443 and it should work 🤞 