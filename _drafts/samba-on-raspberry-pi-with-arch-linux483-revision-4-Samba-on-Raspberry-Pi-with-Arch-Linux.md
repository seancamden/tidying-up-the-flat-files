---
id: 488
title: Samba on Raspberry Pi with Arch Linux
date: 2012-11-04T10:57:53+00:00
author: seancamden
layout: revision
guid: http://www.seancamden.com/2012/11/04/483-revision-4/
permalink: /?p=488
---
[<img src="http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png" alt="Arch Liux Arm" title="arch-linux-arm" width="400" height="89" class="alignnone size-full wp-image-484" srcset="http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm.png 400w, http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm-300x66.png 300w" sizes="(max-width: 400px) 100vw, 400px" />](http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png)
  
I followed [Samba for Arch Linux](https://wiki.archlinux.org/index.php/Samba) and the [Arch Linux Arm Guide to Samba](http://archlinuxarm.org/support/guides/applications/samba) to get Samba working on my Raspberry Pi, but neither told the whole story.

This version of Arch Arm is using [systemd](https://wiki.archlinux.org/index.php/Systemd) to manage services, so there is no /etc/rc.conf file to edit and no `rc.d` command available to start anything. One simply types `systemctl start smbd.service` to make it go.