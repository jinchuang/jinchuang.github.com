---
layout: post
title: VMware CentOS 6.6 桥接网络配置无法解析域名的终极解决办法
date: 2016-06-01
tags: Linux
category: Linux

---

***

今天在VMware中安装了一个BasicServer版的CentOS 6.6，使用的桥接网络配置，之后手动配置了
一些基本的网络设置后，发现更换的更新源无法makecache，找了下原因，发现是域名无法解析的问题，
于是又设置了一遍:

* /etc/sysconfig/network-scripts/ifcfg-eth0
* /etc/sysconfig/network
* /etc/resovl.conf
* /etc/hosts

可是，设置完成之后，在ping了一下百度，还是无法解析，最后一顿折腾，发现了原因：

必须要在/etc/sysconfig/network-scripts/ifcfg-eth0 中设置好DNS1=114.114.114.114

DNS2=4.4.4.4

好低能啊...
