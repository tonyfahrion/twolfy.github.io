---
layout: post
title: How to access env-vars for CustomLog within apache
categories:
- quickFAQ
tags:
- Apache - httpd
- log
- customlog
- logformat
---
You need the modifier "e" after the variable - described here: http://httpd.apache.org/docs/2.2/mod/mod_log_config.html#formats


Example:


<pre>LogFormat "%h %l %u %t \"%r\" %&gt;s %bRequest: %U%q\n\tSession: %{BALANCER_SESSION_STICKY}e \n\tRoute: %{BALANCER_SESSION_ROUTE}e\n\tWorker: %{BALANCER_WORKER_ROUTE}e\n\tFEHLER: %{BALANCER_ROUTE_CHANGED}e\n\tCookie: %{Cookie}i\n" debugBalancer
CustomLog /var/log/apache2/debugBalancer.log debugBalancer
</pre>
