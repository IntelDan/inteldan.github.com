---
layout: post
title: "Be carefull to find the source of error"
description: ""
category: 
tags: []
---
{% include JB/setup %}


>error: unresolved symbols remain  
"configuro/linker.cmd", line 188: error: undefined symbol  
   "ti_sysbios_knl_Task_Object__table__V" used in expression  
error: errors encountered during linking;  
   "/home/changer/WIFI_DVR/tmp/Video_M3/INVO_WIFI_DVR_video/debug/INVO_WIFI_DVR  
   _video.xem3" not built
   
This error may look strange and I even don't know what to do. How can this error happens?

Don't be panic, and stop to search the web if your project is big and there are many output message, just look the former output compile message and  there may be another error, which is the real "evil".

> error: cannot find file  
   "/mnt/hgfs/DVR/Video_M3/DVR/configuro/package/cfg/Video_
   pem3.oem3"  
error: cannot find file  
   "/mnt/hgfs/DVR/Video_M3/DVR/configuro/package/cfg/Video_  
   pem3.src/ipc/ipc.lib"  
error: cannot find file  
   "/mnt/hgfs/IDVR/Video_M3/DVR/configuro/package/cfg/Video_  
   pem3.src/sysbios/sysbios.lib"  
warning: creating output section ".plt" without a SECTIONS specification

I have change the path "*/mnt/hgfs/*" to another in rules.mk or another makerules, but this process is still to find files in it. So just make clean and rebuild it ---**Done**.

So the title of this article may change to "*Don't forget to make clean!*".

