---
layout: post
title:  "Stop ads from entering your home using Pi-hole"
date:   2017-02-07 13:28:22 +0200
description: No more Ads AND a faster home network? Sounds like a win-win...
tags: ["raspberry", "pi", "tips"]
ShowToc: false
---
![Image for post](/images/pihole.jpg)

I don’t like ads and I feel no shame in admitting I use a combination of ad-blockers (uBlock) and ‘do-not-track-me’-plugins (Ghostery & Blur) in Safari. Come on, be honest; who isn’t… On the other side: sites I like get whitelisted. Easy.

However with all these different devices in your household it gets a bit confusing and cumbersome to install ad-blockers on all your devices. How great would it be if you could block ads at your router? If you could stop ads from even entering your house? Not only will you stop seeing ads. Your network-speeds will increase because it is no longer trying to load or all these ads.

If you have a Raspberry Pi you can easily do this. You can setup the Raspberry Pi as a DNS and direct all your traffic trough the Rasberry Pi. Sounds difficult but it is not. The guys from [Pi-hole](https://pi-hole.net/) have developed a **network-wide ad-blocking application**. Via a simple and single curl command you are ready to go.

`curl -sSL https://install.pi-hole.net | bash`

First SSH into your Pi, paste the above command in the Terminal and Pi-hole will install. The only thing left is [configuring your router](https://discourse.pi-hole.net/t/how-do-i-configure-my-devices-to-use-pi-hole-as-their-dns-server/245) so all traffic is routed through your Pi. 10 minutes tops.

Pi-hole even comes with a GUI Admin Console so you can easily blacklist and/or whitelist ad-domains. This console can be found at [http://yourdomain/admin/index.php](http://yourdomain/admin/index.php)

Want to know more about Pi-hole? Check out their [Userspace](https://discourse.pi-hole.net/) and [subreddit](https://www.reddit.com/r/pihole/).