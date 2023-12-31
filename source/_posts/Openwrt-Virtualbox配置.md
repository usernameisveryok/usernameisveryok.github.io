---
title: Openwrt+Virtualbox组网教程
date: 2023-12-20 20:10:47
tags: 虚拟化 网络安全 openwrt
---

最近在尝试本地完全虚拟化一个网络用来做测试，主要参考 openwrt 的文档进行配置
以下是踩的几个坑

- virtualbox 采用 hostonly adapter 便于宿主机使用 ssh 连接各个子网中的虚拟机，子网 ip 配置为 x.x.x.2,禁用 DHCP 功能，此功能由 openwrt 实现。
- 第一个 adaper 为 lan，第二个接口为 wan，这样对于网关路由器，只需要修改 lan 的 ip 地址为子网地址:.1 即可
- 对应主机加入子网，直接连接对应适配器即可。
