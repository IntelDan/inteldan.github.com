---
layout: post
title: "fail to install build essential"
description: ""
category: "ubuntu"
tags: ['ubuntu', 'source.list']
---
{% include JB/setup %}

when I want to install the package build essential, there is error that

><font color="red">The following packages have unmet dependencies:
>
> build-essential : Depends: libc6-dev but it is not going to be installed or
>
>                            libc-dev
>
>                   Depends: g++ (>= 4:4.4.3) but it is not going to be installed
>
> E: Unable to correct problems, you have held broken packages.</font>

I have a source.list which workes well under 12.04LTS, I think it would also can be used in 14.04LTS as the source.list doesn't point
out about any ubuntu version. It seems to work well after I change the source to that, but according to the error that happens, I find that the cause
may be my source.list. So I search the 14.04LTS source, and change again. It works well.


> [http://chenrongya.blog.163.com/blog/static/8747419620143185103297/](http://chenrongya.blog.163.com/blog/static/8747419620143185103297/)

I only past the source of 163 mirror, and now it works well.
