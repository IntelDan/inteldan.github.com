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

TODO: [reference](http://my.oschina.net/shelllife/blog/123482)  
- /dev/mtdN 是MTD架构中实现的mtd分区所对应的字符设备(将mtd设备分成多个区，每个区就为一个字符设备)，其里面添加了一些ioctl，支持很多命令，如MEMGETINFO，MEMERASE等。mtd-utils中的flash_eraseall等工具，就是以这些ioctl为基础而实现的工具，实现一些关于Flash的操作。  
- 实际上mtdN和mtdblockN描述的是同一个MTD分区，对应同一个硬件分区，两者的大小是一样的，只不过是MTD设备层提供给上层的视图不一样，给上层提供了字符和块设备两种操作视图——为了上层使用的便利和需要，比如mount命令的需求，你只能挂载块设备(有文件系统)，而不能对字符设备进行挂载，否则会出现上面的现象2:无效参数。这里对于mtd和mtdblock设备的使用场景进行简单总结：

    mtd-utils工具只能应用与/dev/mtdN的MTD字符设备  
    mount、umount命令只对/dev/mtdblockN的MTD块设备有效  
    /dev/mtdN和/dev/mtdblockN是同一个MTD设备的同一个分区（N一样）  
