---
layout: post
title: "如何更换octpress主题"
date: 2012-06-07 06:12
comments: true
categories: 
---

Octopress在2.0之后添加了source/_includes/custom目录
> source/
    _includes/   #关于布局的目录
       custom/   # 这个目录可以调整页面头部,导航栏,页脚以及边栏
       asides/   # 这个目录关于主题边栏部分
       post/     # 这个目录关于帖子的元数据,分享以及评论部分
    _layouts/    # 这个目录关于页面布局,帖子以及类型归档等


> mv index.html blog/index.html
