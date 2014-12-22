---
layout: post
title: "make the netwok icon of Ubuntu12.04 working properly"
description: ""
category: 'Ubuntu'
tags: ['network', 'Ubuntu']
---
{% include JB/setup %}
**After** upgrading my ubuntu from 10.04 to 12.04, there is still a problem that my network is working, but the netwok icon in is always a state that my network is bad which with a red cross.

Open the file with root previllege

> /etc/NetworkManager/NetworkManager.conf

    [ifupdown]  
    managed=false

Then change the false to true and use these command to restart the networkManager.

> sudo service network-manager stop  
sudo rm /var/lib/NetworkManager/NetworkManager.state
sudo service network-manager start

Then my network icon is well-looking.

*TODO*
When I upgraded the 10.04, I have finished many problem.  
One which is very weried I changed the disk interface twice times.
* After restart, I can't enter OS only with a blinking cursor. I change the interface frome AHCI to IDE.
* When I success installing the update package, the problem is the same to last one except the blinking area is more huge.
Then I change the interface back to AHCI.