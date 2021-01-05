---
layout: post
title:  "Bug Reporting"
date:   2020-10-13 18:27:22 +0200
categories: update
---
If you work in a company selling products digitally everyone needs to learn how to properly debug before reporting a bug/issue to the incident managers or the platform-/dev-team.

It happens way too often that a bug is sort of thrown over the fence. Reporter: _"Hey Carlo, I cannot perform {INSERT ACTION HERE}, it's not working as how I expected it to work, please investigate..."_ OK... now what?

### Before I jump into 'investigation-mode' I would need at the minimum the following questions answered:
1. The most important one of all is on Reproducability: **can you tell me how I can reproduce it on my machine?** If we cannot reproduce it it cannot be investigated & fixed.
* It's honestly not useful that it happens on _your_ laptop/mobile (only?) and that perhaps it _might_ happen to more users. 
2. Also, what did you do to debug it? (Assuming a website-bug) Did you:
* try it in other browsers;
* clear you cache / delete your cookies;
* try it in incognito mode;
* try it on another device;
* try it without VPN or wifi (yes, also try on your phone's hotspot);
* make sure no plugins or extensions are interfering;
* make sure you are on the correct URL (http vs. https, www vs non-www)
3. Are there signs of multiple users being affected by the bug? If so, how many per hour/day/week?
* This helps in determining the impact & priority from a P4 (low-impact but still needs to be fixed) to P1 (production defect, all users are affected, drop everything and start fixing it)

If you tried all the above and it's clear there is something going on then we can go to the next step. The actual bug report. 

### A good bug report:
* is created by the bug reporter (and not the indident-managers or dev-team)
* contains all info to reproduce the issue
    * URLs
    * Browser & Operating System
    * Expected vs Received result
    * Screenshots
    * [Share a HAR-file](/assets/docs/har_file.pdf) 
* is filed in the proper system (e.g. Jira/Slack) 
* follows the agreed upon bug report-structure of the organization
* is assigned to the proper colleague

