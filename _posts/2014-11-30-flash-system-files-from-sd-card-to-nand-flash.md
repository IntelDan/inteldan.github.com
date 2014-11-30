---
layout: post
title: "flash system files from sd card to nand flash"
description: ""
category: 'embedded'
tags: ['8127', 'embedded']
---
{% include JB/setup %}

The other method to flash uboot or uImage to 8127 nand flash.

The process is :

    mkdir /dev/mtdblock
    cat /proc/mtd
    mount /dev/mmcblock0p1 /media
    /*xx represent uboot or uImage ,x represent the nand flash block number*/
    cp /media/xx /dev/mtdx 
