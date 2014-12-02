---
date: 2014-12-02 11:12:42
layout: post
title: 如何使用xcodebuild在命令行编译iOS工程
categories: iOS
tags: 学习笔记 xcodebuild
---

1.	钥匙串访问->证书助理->从证书颁发机构请求证书。生成证书

2.1	在开发者网站申请新的certificate，下载到本地打开。注：请求文件在步骤1中生成。

`![](/assets/create_cer.png)`

2.2	在开发者网站添加distribute provisioning profile，下载到本地打开。注意app id。使用步骤2生成的证书。

3.	工程中设置code signing identity为don’t code sign

	provisioning profile为automatic
	
	terminal进入工程文件夹，先打包xcarchive

	`xcodebuild -scheme MyiOSApp archive -archivePath /Users/username/Desktop/MyiOSApp.xcarchive`

	ipa生成的时候指定certificate及provisioning profile。使用上一行生成的xcarchive文件。

	`xcodebuild -exportArchive -exportFormat ipa -archivePath "/Users/username/Desktop/MyiOSApp.xcarchive" -exportPath "/Users/username/Desktop/MyiOSApp.ipa" -exportProvisioningProfile "MyCompany Distribution Profile" -exportSigningIdentity "Developer ID Application: My Software Company"`

	注：MyCompany Distribution Profile及Developer ID Application: My Software Company之前相应的文件下载打开，可以在管理器中可以查看名称

4.	试一下能否使用xcode或itunes直接安装到真机上。注：真机需要注册到开发者账号上。

参考贴：`[http://stackoverflow.com/questions/2664885/xcode-build-and-archive-from-command-line](http://stackoverflow.com/questions/2664885/xcode-build-and-archive-from-command-line)`