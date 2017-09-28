---
layout: post
title:  "linphone-android编译安装1"
date:   2017-09-27 14:06:05
categories: Front-end JavaScript
excerpt: linphone-android编译和安装。
---

* content
{:toc}


## 关于linphone的编译和安装1
voip的客户端实在不少，zipper, xlite，linphone等。。，其中linphone算是个老牌的voip客户端了，功能非常庞大，但是也带来了它的庞大的‘体积‘这个弊端，源代码下载下来要有1.3个G左右(最新版), 比服务器(例如freeswitch)都大，编译好后甚至达到3.3G(说实话，个人觉得它太臃肿了，成了它最大的缺点)，好了，言归正传，本文简单讲下linphone-android的编译(linphone-desktop, linphone-iphone等编译相对简单，最复杂的就是linphone-android, 所以这里以android客户端的编译为例)：
1. 下载：个人建议不要从官方git下载(git://git.linphone.org/linphone-android.git --recursive)，笔者就在这个坑里浪费了不少时间，一个是速度很慢，然后个吧小时后看似下载完毕了，没有报错，其实某些模块没有下载成功，然后编译中间的错误信息也看不出来问题所在。
建议下载地址： 2017年09月27日网页链接，笔者验证过下载比官网快很多(和官网同步是最新版本).
2. readme: 下载完毕，打开linphone-android/README.md，按照里面的编译要求来:
2.1 安装android sdk (版本必须包括api 25.2.3), 以笔者电脑为例，下载到~/Library/Android/sdk,那么在bashrc文件中(根据不同的shell，配置文件名不同)
2.2 下载安装android ndk(版本必须为r11c或者r13b), 譬如下载到~/Library/Android/sdk/android-ndk-r13b/
2.3 在shell的配置文件中(例如bashrc)中export相关的环境变量
        export ANDROID_HOME=~/Library/Android/sdk
        export ANDROID_NDK=~/Library/Android/sdk/android-ndk-r13b/
        export PATH=$ANDROID_HOME:$ANDROID_HOME/platform-tools:$ANDROID_HOME/tools:$ANDROID_NDK:$PATH
3. 解析来按照README.md里的步骤3、4、5、6进行依赖安装、配置、编译和安装apk
注：如果第一次编译过程中出现问题，多半是git clone ...过程出问题没有下载全，建议删除linphone-android目录重新下载，好在github速度很快，一般最多重复2次一定可以成功完整的下载整个linphone-android项目工程。
