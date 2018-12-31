---
id: 483
title: Samba on Raspberry Pi with Arch Linux
date: 2012-11-04T11:09:11+00:00
author: seancamden
layout: post
guid: http://www.seancamden.com/?p=483
permalink: /?p=483
st_cached:
  - '<ul class="socialize-this"><li><a href="http://del.icio.us/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483&title=Samba+on+Raspberry+Pi+with+Arch+Linux" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/del.png" width="48px" height="48px" alt="Delicious" title="Delicious" /></a></li><li><a href="http://www.facebook.com/sharer.php?u=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483&t=Samba+on+Raspberry+Pi+with+Arch+Linux" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/facebook.png" width="48px" height="48px" alt="Facebook" title="Facebook" /></a></li><li><a href="http://digg.com/submit?phase=2&url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/digg.png" width="48px" height="48px" alt="Digg" title="Digg" /></a></li><li><a href="http://www.reddit.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483&title=Samba+on+Raspberry+Pi+with+Arch+Linux" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/reddit.png" width="48px" height="48px" alt="Reddit" title="Reddit" /></a></li><li><a href="http://www.stumbleupon.com/submit?url=http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483&title=Samba+on+Raspberry+Pi+with+Arch+Linux" target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/stumble.png" width="48px" height="48px" alt="StumbleUpon" title="StumbleUpon" /></a></li><li><a href="http://twitter.com/home?status=Currently Reading http%3A%2F%2Fwww.seancamden.com%2F%3Fp%3D483"  target="_blank"><img src="http://www.seancamden.com/wp-content/plugins/socialize-this/widgets/alteredicons/twitter.png" width="48px" height="48px" alt="Twitter" title="Twitter" /></a></li></ul>'
st_cached_time:
  - "1352050940"
st_tiny_url:
  - http://is.gd/z0vwdO
st_twitter:
  - "0"
st_reddit:
  - 'a:3:{s:9:"permalink";s:0:"";s:5:"score";i:0;s:12:"num_comments";i:0;}'
st_social_score:
  - "0"
st_last_socialized:
  - "1390063551"
st_facebook:
  - "0"
st_googleplusones:
  - "0"
---
[<img src="http://www.seancamden.com/wp-content/uploads/2012/11/raspberrypi1.jpeg" alt="" title="raspberrypi" width="204" height="247" class="alignnone size-full wp-image-490" />](http://www.seancamden.com/wp-content/uploads/2012/11/raspberrypi1.jpeg)
  
[<img src="http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png" alt="Arch Liux Arm" title="arch-linux-arm" width="400" height="89" class="alignnone size-full wp-image-484" srcset="http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm.png 400w, http://seancamden.cosm/wp-content/uploads/2012/11/arch-linux-arm-300x66.png 300w" sizes="(max-width: 400px) 100vw, 400px" />](http://www.seancamden.com/wp-content/uploads/2012/11/arch-linux-arm.png)
  
I followed [Samba for Arch Linux](https://wiki.archlinux.org/index.php/Samba) and the [Arch Linux Arm Guide to Samba](http://archlinuxarm.org/support/guides/applications/samba) to get Samba working on my [Raspberry Pi](http://www.raspberrypi.org/).

This version of Arch Arm is using [systemd](https://wiki.archlinux.org/index.php/Systemd) to manage services, so there is no more `/etc/rc.conf` file to edit and no `rc.d` command available to start anything (as the Arch Linux Arm Guide instructs). One simply types `systemctl start smbd.service` to make it go (after configuring `/etc/samba/smb.conf`, of course).