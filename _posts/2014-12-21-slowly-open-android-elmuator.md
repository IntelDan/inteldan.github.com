---
layout: post
title: "Slowly open android elmuator"
description: "quickly open android elmuator"
category: 'Android'
tags: ['Android']
---
{% include JB/setup %}


I use the  Intel x86 elmuator accelerator to open android elmuator, and select the cpu type as "Intel x86". But when the elmuator begin booting and there are logs such as:

> Open HAX device failed emulator:

What's more ,the booting time is very long. It means that you have't install the HAXM, and *what you see in the SDK manager is just the installer and that isn't indicate that you have install the program*. So just go to SDK's folder / Extras / Hardware_Accelerated_Execution_Manager and install the intelhaxm.exe.

Then the elmuator will boots up very quickly.

Another foolish thing I did is to  open one elmuator twice and of cousre the second will boot very very slowly which may be out of  my tolerant.

[reference](http://stackoverflow.com/questions/20857256/failed-to-open-the-hax-device-hax-is-not-working-and-emulator-runs-in-emulation)
