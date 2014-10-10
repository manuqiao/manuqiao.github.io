---
date: 2014-10-10 14:21:13
layout: post
title: Map Kit用圆点显示当前用户位置
categories: iOS
tags: 学习笔记 MapKit
---

在
    - (MKAnnotationView *)mapView:(MKMapView *)mapView viewForAnnotation:(id <MKAnnotation>)annotation
实现方法中，返回nil，即显示圆点。
判断是否为MKUserLocation即能区分当前位置或者自定义位置。