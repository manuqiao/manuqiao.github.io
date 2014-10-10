---
date: 2014-10-10 13:41:54
layout: post
title: iOS8 获取位置信息
categories: iOS
tags: 学习笔记 MapKit
---

1.    新建CLLocationManager实例，调用`requestAlwaysAuthorization`或`requestWhenInUseAuthorization`。

2.    在info.plist中加入`NSLocationAlwaysUsageDescription`或`NSLocationWhenInUseUsageDescription`字段，键值为获取位置信息权限时的提示信息。