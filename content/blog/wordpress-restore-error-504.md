---
layout: post
title:  "Getting a 504 error on Wordpress?"
date:   2022-02-20 10:28:00 +0200
categories: wordpress
description: It's probably happening because you are trying to handle a relatively large amount of data.
tags: ["wordpress", "tips"]
ShowToc: false
draft: false
---

So I've been trying to restore the backup of my Wordpress site and I've been getting a 504 error. I've tried to use the [Wordpress REST API](https://developer.wordpress.org/rest-api/reference/) to restore the backup but it's not working. Regardless of the reason, I've been getting the error for a long time.

Check first with your hosting provider if they are running any proxies. If not, you can solve the issue by adding a `.user.ini` file to your Wordpress site. 

Easies way to do that is to install [Filezilla](https://filezilla-project.org/) and then connect to your Wordpress site.

In the httpdocs folder of your Wordpress site, create a new file called `.user.ini`

![user-ini](/images/user-ini.png)


Then open the `.user.ini` file and add the following lines:

```
memory_limit = 256M
max_execution_time = 300
upload_max_filesize = 64M
post_max_size = 64M
```

Save it and make sure you close the file and it's uploaded again by Filezilla.

Now you should be able to handle larger files on your Wordpress server and restore the backup.


