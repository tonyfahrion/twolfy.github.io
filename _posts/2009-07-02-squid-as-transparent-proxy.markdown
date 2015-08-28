---
layout: post
title: Squid as transparent proxy...
categories:
- serverServices
tags:
- error
- squid
- failure
- transparent proxy
- proxy
---
Okay, currently I'm setting up a squid-cache daemon as transparent proxy. While I'm doing this I like to describe the progress and in which errors I'm running.


Now I'm finished with the configuration - so I have to look back what I've done. I will post it later on... now I like to document my failure.


I tried to start squid and got the following error-message:


<pre>Starting Squid HTTP proxy: squid2009/07/02 11:41:14| parseConfigFile: squid.conf:20 unrecognized: 'httpd_accel_host'
2009/07/02 11:41:14| parseConfigFile: squid.conf:21 unrecognized: 'httpd_accel_port'
2009/07/02 11:41:14| parseConfigFile: squid.conf:22 unrecognized: 'httpd_accel_with_proxy'
2009/07/02 11:41:14| parseConfigFile: squid.conf:23 unrecognized: 'httpd_accel_uses_host_header'
2009/07/02 11:41:14| ACL name 'all' not defined!</pre>
I get those configuration-keys from <a href="http://www.linuxdevcenter.com/pub/a/linux/2001/10/25/transparent_proxy.html">this</a>... but squid-cache also doesn't show them in their documentation. Instead they say something about...


<pre>http_port 80 transparent</pre>
So I replaced those 4 lines with this single line above and now it works!


Also squid seems to need the ACL "all" - okay, that's really easy to fix :)


<pre>acl all src 0.0.0.0/0</pre>
So long...


