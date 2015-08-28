---
layout: post
title: Your OpenStack Cloud, How to list VMs via command line
categories:
- Virtualization
- quickFAQ
- OpenStack
tags:
- OpenStack
- Interactive Cloud OS
- cloudcomputing
- Cloud
- CLI
- Nova
- featured
---
It's pretty easy to list all VMs in your OpenStack Cloud via CLI (command line).


You just need to do 3 Steps:


<ul>
<li>login into your OpenStack host</li>
<li>source the credentials for your OpenStack environment</li>
<li>list the instances</li>
</ul>
Pratical, you need to type in:



{% highlight bash linenos %}
# inline settings from shell.config.sh (use the command "source" or just a "." dot)
source /etc/openstack/shell.config.sh
# list available VMs
nova list
{% endhighlight %}

And here is an example from the above:

[caption id="attachment_265" align="alignnone" width="300"]<a href="/files/2013/11/cmd_nova_list_0.97-20.png"><img class="size-medium wp-image-265" alt="OpenStack list instances via CLI (command line)" src="/files/2013/11/cmd_nova_list_0.97-20.png" width="300" height="44" /></a> In this example, we use the "." dot, instead of the command "source"[/caption]


Note: This will work with the <a href="http://cloudos.internet.de">Interactive Cloud OS</a> out-of-the-box!


