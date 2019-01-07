---
id: 495
title: Samba on Raspberry Pi with Arch Linux
date: 2012-11-04T11:10:16+00:00
author: seancamden
layout: revision
guid: http://www.seancamden.com/2012/11/04/483-autosave/
permalink: /?p=495
---
[<img src="http://www.seancamden.com/wp-content/uploads/2012/11/raspberrypi1.jpeg" alt="" title="raspberrypi" width="204" height="247" class="alignnone size-full wp-image-490" />](http://www.seancamden.com/wp-content/uploads/2012/11/raspberrypi1.jpeg)
  
[<img src="http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png" alt="Arch Liux Arm" title="arch-linux-arm" width="400" height="89" class="alignnone size-full wp-image-484" srcset="http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm.png 400w, http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm-300x66.png 300w" sizes="(max-width: 400px) 100vw, 400px" />](http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png)
  
I followed [Samba for Arch Linux](https://wiki.archlinux.org/index.php/Samba) and the [Arch Linux Arm Guide to Samba](http://archlinuxarm.org/support/guides/applications/samba) to get Samba working on my [Raspberry Pi](http://www.raspberrypi.org/).

This version of Arch Arm is using [systemd](https://wiki.archlinux.org/index.php/Systemd) to manage services, so there is no more `/etc/rc.conf` file to edit and no `rc.d` command available to start anything (as the Arch Linux Arm Guide instructs). One simply types `systemctl start smbd.service` to make it go (after configuring .