---
layout: post
title: enable ip forward on linux
tags:
  - linux-server
---

That's easy!

Add

    net.ipv4.ip_forward=1

to /etc/sysctl.conf and execute the command:

    sysctl -p

DONE

Normaly you should already find a already prepared line, so you just need to uncomment it. 


