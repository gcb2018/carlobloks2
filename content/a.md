---
layout: post
title:  "Downgrade Unifi Controller from 6.0.xx to 5.14.23"
date:   2020-12-10 21:27:22 +0200
categories: update
---
## Please don't update your Unifi controller to 6.0.xx
 
You will lose a couple great features that might mess up your network. Especially if you used the setup guide by [The Hook Up](https://www.youtube.com/watch?v=p3SfeQTaaxw). Think your VLAN settings for your WLAN and WLAN override configurations.

If you have already done this and regret it: follow the steps below to return to your previous settings.

So step 1 is: make sure you have scheduled backups turned on, else it's too late anyway...

Then SSH into your controller
```ssh {user}@{controller-ip}``` and enter your password.

Then enter the following commands one by one (no worries, your internet will keep working as we are only touching the controller)
```apt purge unifi -y```

```rm unifi_sysvinit_all.deb*``` 

```wget https://dl.ui.com/unifi/5.14.23/unifi_sysvinit_all.deb```

```dpkg -i unifi_sysvinit_all.deb```

```rm unifi_sysvinit_all.deb```

Then visit the controller via https://localhost:8443 or https://{controller-ip}:8443. here you can restore from your backup by uploading the file
