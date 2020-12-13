---
layout: post
title: SSD Formatting and Install in Ubuntu 19.04
date: '2019-05-05'
draft: false
tags: [
  "ubuntu",
  "installation"
]
---

Today I upgraded the base 256 GB SSD (2.5 mm) on my Thinkpad T460 to a 1 TB [Samsung 860 EVO](https://www.amazon.com/gp/product/B078DPCY3T/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1).

It took me a few google searches to learn how to make the transition. In the end, I used Tuxboot to make a bootable Clonezilla USB drive, and then GParted to resize my partition. Here's what I did step-by-step:

0. Connect your new SSD via USB. I used [a StarTech cable from Amazon](https://www.amazon.com/gp/product/B00HJZJI84/ref=ppx_yo_dt_b_asin_title_o00_s00?ie=UTF8&psc=1). 
1. Download Tuxboot (from the [SourceForce Repo](https://sourceforge.net/projects/tuxboot/files/)).
2. Extract and install Tuxboot.
    * I needed to run `apt-get install libqt4-dev`, `apt-get install mtools`, and then `./INSTALL`.
3. Run `sudo ./tuxboot` to run the tuxboot GUI. On the first line, select "On-Line Distribution" and "clonezilla_live_stable", connect an empty USB drive, select that drive on the last line, and click "OK".
4. After tuxboot makes a bootable clonezilla USB, boot from that USB.
5. Follow the disk-to-disk clone tutorial from on the [Clonezilla website](https://clonezilla.org/show-live-doc-content.php?topic=clonezilla-live/doc/03_Disk_to_disk_clone).
6. After restarting, download Gparted with `sudo apt-get gparted`. Follow the instructions in the GUI to resize the new disk to the full ~950 GB. 
7. Physically install the new SSD, and you should be good to go!