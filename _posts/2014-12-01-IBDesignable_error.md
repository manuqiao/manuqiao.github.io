---
date: 2014-12-01 11:03:54
layout: post
title: IBDesignable常见问题
categories: iOS
tags: 错误处理 xib
---

1.如果遇到IBDesignable编译期报错

IB Designables: Failed to update auto layout status: Interface Builder Cocoa Touch Tool raised a "NSInvalidArgumentException" exception: Unable to parse constraint format: 
Unable to interpret '|' character, because the related view doesn't have a superview 
H:|-(>=50)-[view(100)] 
                      ^

IB Designables: Failed to update auto layout status: Interface Builder Cocoa Touch Tool raised a "NSInvalidArgumentException" exception: Unable to parse constraint format: 
Unable to interpret '|' character, because the related view doesn't have a superview 
H:|-(>=50)-[view(100)] 
                      ^

尝试在设置constraints前，先吧view加入superview

2.如果遇到view无法显示

可能是于autoresizing冲突
尝试[view setTranslatesAutoresizingMaskIntoConstraints:NO];