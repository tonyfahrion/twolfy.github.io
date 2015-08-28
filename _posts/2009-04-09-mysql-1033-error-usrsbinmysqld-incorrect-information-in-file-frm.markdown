---
layout: post
title: 'MySQL-1033 [ERROR] /usr/sbin/mysqld: Incorrect information in file: *.frm'
date: 2009-04-09
categories:
- quickFAQ
tags:
- MySQL
- error
- errors
- message
- innodb_log_file_size
- '1033'
---

This error occured when you change your
  innodb_log_file_size
and already have some Innodb-tables. I wasn't success fixing it while keeping the new settings. But you only have to change the value to the original value, restart MySQL and be happy...


This seems to be a bug - but I don't know it. Many people reported the same issue!


*Please MySQL guys, don't call it "log" if it was that importend to run the server!*




