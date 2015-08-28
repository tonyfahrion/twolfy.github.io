---
layout: post
title: Debug Binaries
categories:
- quickFAQ
tags:
- Hacks
- tools
- debug
- shared libraries
---

Just prepend your command with the following string

    LD_DEBUG=files

and it will dump which shared libraries were used.

E.g.:

    LD_DEBUG=files ls

