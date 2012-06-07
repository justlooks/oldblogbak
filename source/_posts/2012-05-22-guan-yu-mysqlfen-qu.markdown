---
layout: post
title: "关于mysql分区"
date: 2012-05-22 01:43
comments: true
categories: 
published: false
---

Mysql对于hash和key分区模式有两种键值映射模式,liner和regular

1. liner映射模式
  首先决定V值,算法为(如果有N个分区)
  POWER(2, CEILING( LOG(2,N) ) )
  比如在6个分区情况下,V值为8
  
  然后决定存储到哪个分区,采用对V值取余运算
  T=f(列值)&(V-1)
  如果计算得到的值T不小于总分区数的话,则进行额外运算
  T&CEILING(V/2)

优点是添加,删除合并以及分割分区非常快,缺点是分区的数据不是均匀分布

2. 
  

