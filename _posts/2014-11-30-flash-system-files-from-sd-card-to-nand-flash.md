---
layout: post
title: "flash system files from sd card to nand flash"
description: ""
category: 'embedded'
tags: ['8127', 'embedded']
---
{% include JB/setup %}

The other method to flash uboot or uImage to 8127 nand flash.

(After the system started up using sd card.)


The process is :

    mknod /dev/mtdblock
    cat /proc/mtd
    mount /dev/mmcblock0p1 /media
    /*x represent the nand flash block number, if we need to refresh the block in the furture*/
    flash_erase /dev/mtdx
    /*xx represent uboot or uImage ,x represent the nand flash block number*/
    cp /media/xx /dev/mtdblockx
    
Careful:

- mtdx is a  char device.
- mtdblockx is a block device

TODO: [more conclude](http://my.oschina.net/shelllife/blog/123482)
