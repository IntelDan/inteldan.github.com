---
layout: post
title: "push through ssh"
description: ""
category: 'git'
tags: ['github', 'git']
---
{% include JB/setup %}

If you clone the git reprosity through https, then you will be required to input your username and password when pushing or pulling to github.

So in order to avoid this annoying process, we can clone the reprosity through ssh, which need to configure ssh key, and clone like this

> git@github.com:UserName/reprosityname.git