---
layout: post
title:  "Manually upgrading Unifi firmware"
date:   2021-03-02 12:45:00 +0200
description: Manually upgrading Unifi firmware if it does not work via the controller 
tags: ["unifi", "tips"]
ShowToc: false
---
So you might have tried upgrading your Unifi devices via the controller and for some reason it did not work. Usually this means that the download of the firmware-file failed and chances are big this happens for one of your Switches. In my usecase I am manually upgrading the US-8-60W.

First you download the latest ```.bin```-file from the [Downloads](https://www.ui.com/download/unifi-switching-routing/unifi-switch-8-60w) page. Make sure to put it in the Downloads-folder on your Macbook in order to follow the steps I have specified below, else you need aadjust accordingly.

Open the Terminal app and add the following command:

```scp /Users/{macbook-username}]/Downloads/{bin-file} {unifi_ssh_username}@{ip-address_device}:/tmp/fwupdate.bin```

Adjusted for my details it looks like this:

```scp /Users/giancarlobloks/Downloads/US.bcm5334x_5.43.23+12533.201223.0319.bin carlobloks@10.0.1.2:/tmp/fwupdate.bin```

If this is the first time establishing an ssh connection to the device it will ask you if you want to continue connecting. Type 'yes' and press Enter. 

Add the password. 

If you don't remember the username/password to ssh into your devices you can check them in your controller. Go to Settings > System Settings > Controller Configuration > Device SSH Authentication. If you did not set it up yet you can do so now. 

The Terminal will show you the progress of uploading the ```.bin```-file to ```/tmp/fwupdate.bin``` which for me took about 20 seconds. 

After the file is uploaded you now need to ssh into the device and execute the upgrade command:

```ssh carlobloks@10.0.1.2```

Add password. (this is the same user/password you used before to upload the file). Then:

```syswrapper.sh upgrade2 &```

You will see the progress again and in total just give it 5 minutes and reload the controller to verify the upgraded firmware version.

That's it.








