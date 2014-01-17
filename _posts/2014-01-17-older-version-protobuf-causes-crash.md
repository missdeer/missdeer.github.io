---
layout: post
title: "旧版本Protobuf在Serializing方法crash"
categories: Coding
description: 旧版本Protobuf在Serializing方法crash
key: Coding
---
花了几天时间，把原本基于XML的IPC重要部分都改成用Protobuf了，之前以为会大幅度提高运行效率，结果发现原本用RapidXML库生成消息，比填充Protobuf结构慢不了多少。不过可以肯定的是，消息长度缩短为差不多是原来的1/4了，原本16KB左右，之后4KB多点。

不过昨天发现有一处调用Serialization方法，总是crash，找不出原因，有可能一直不crash，有可能一直crash。很沮丧，于是本来就有点犹豫要不要把代码merge到master，彻底停下来了。

今天又试了试下载最新的2.5版本的Protobuf源代码，自己build，试了gcc和icc，debug和release，都不crash了，而CentOS仓库中的是2.3版本。看来就是升级到新版本就修复了这个bug了。

