---
layout: post
title: Solution for the KVM virtio Windows 2008 (R2) problem
categories:
- Virtualization
tags:
- e1000
- windows
- server
- kvm
- libvirt
- network
---
Hi all!

Since Windows 2k8 (R2), Windows 7 and may be Windows Vista (haven't it tested jet), drivers have to be signed to be installable. As the kvm virtio-driver for Windows aren't signed, you can't install them. In the wild, there are some solutions out there. But they are really not what you want!

KVM with libvirt supports a really easy solution - out of the box!

You won't get the best available network performance with this solution! But it should be acceptable...

Okay, enough flam ware now the solution. You could # select another network device emulation ... that's it ^^

How this works is described on [http://libvirt.org/formatdomain.html#elementsNICSModel][libvirt].

Switch the following line in your libvirt-host-XML (network-section):

   from: # &lt;model type='virtio'/&gt;
   to:# &lt;model type='e1000'/&gt;

I have tested it with the Intel e1000 driver and it works out of the box with windows 2008 R2 and Windows 7.

[libvirt]: http://libvirt.org/formatdomain.html#elementsNICSModel

