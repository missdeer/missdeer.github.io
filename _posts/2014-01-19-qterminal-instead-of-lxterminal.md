---
layout: post
title: "使用qterminal替代LXTerminal"
categories: Software
description: 使用qterminal替代LXTerminal
key: qterminal LXTerminal
---
发现FreeBSD上的LXterminal很容易在输入长命令时换行错位，于是胡乱覆盖掉前面的内容，就很难好好地输入完一整条长命令。这事在Debian上没遇到过，我也只在Debian上装过LXDE并使用LXTerminal。其他在Linux上用过的Terminal也只有GNOME Terminal和Mate Terminal，感觉吧每种Terminal都是配合自家的DE的，虽然可以混用但心里总是有点疙瘩。

想起还有个非常非常简单且轻量级的qterminal，于是从github取下最新代码来自己build。在FreeBSD上源代码和CMakeLists.txt都需要一点修改，好在很容易。

编译完成后就可以直接使用了，貌似LXTerminal那种换行错位的问题没有了，不过用了一会儿发现一些不足：

* 貌似改不了字体，在FreeBSD上可以改，但改了没变，在Mac OSX上直接不能改；
* 只能强制使用Qt4编译，CMakeLists.txt的依赖里就写死了，现在cmake系统也没有官方支持Qt5，所以也不知道迁移到Qt5有多少问题；
* 在Mac OSX上不是个app bundle，要从另一个terminal里启动；
* 貌似跟fish shell兼容不好，fish shell的自动补全快捷键Ctrl+F不生效，Ctrl+U删除到行首也不生效，其实不一定是跟fish的兼容问题，也许其他shell也一样；

前三条我也许有得闲的时候可以试着改改。先这么用着吧，总比输入命令换行错位好多了。
