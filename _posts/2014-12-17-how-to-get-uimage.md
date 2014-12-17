---
layout: post
title: "how to get uImage"
description: "Rember how to generate an uImage"
category: 'kernel'
tags: ['kernel ','uImage ']
---
{% include JB/setup %}

For the kernel image (uImage) to be built, mkimage utility must be included in the path. mkimage utility is generated
(under tools folder of U-Boot) while building the U-Boot binary.
On successful completion, file uImage will be created in the directory ./arch/arm/boot.

use this command to install mkimage
> sudo apt-get install uboot-mkimage

One question is how the IPNC rdk make uImage under the folder ipnc_psp_argo without having mkimage in *PATH*?
