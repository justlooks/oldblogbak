---
layout: post
title: "Configure octopress outlook"
date: 2012-06-07 07:38
comments: true
categories: octopress
---

mission one:需要在页面增加一个新的page,比如about

--------

首先生成source目录下的about目录,以及内容
	# rake new_page["about/about.html"]
	# rake new_nage["about"]    # 这将在about目录下生成about.markdown文件而不是about.html文件

接着修改导航栏添加到about.html页面的导航
	# cd octopress/source/_includes/custom
	# vi navigation.html

添加如下代码
	<li><a href="{{ root_url }}/about/about.html">About</a></li>

这样在导航栏就有了about页面的导航选项了

需要更新下修改后的octopress代码
	# rake update_source
	# rake generate
	# rake deploy
这样的话更新就体现在github网站上了

----

mission two:添加一个twitter侧栏


2.0版本内建了twitter等第三方插件,如果是老版本的话,更新到最新的octopress代码
	# cd octopress
	# git pull octopress master
	# bundle install
	# rake update_source
	# rake update_style

在octopress/source/_includes/asides目录下有twitter,pinboard等第三方插件,将其拷贝到custom/asides目录下
	# cp source/_includes/asides source/_includes/custom/asides

编辑_config.yml文件,添加下列文本为
	page_asides: [custom/asides/twitter.html]
	

然后更新
	# rake generate
	# rake deploy 


----

mission three: 修改字体

在google web font中选择一种
编辑source/_includes/custom/head.html文件,添加代码
	<link href='http://fonts.googleapis.com/css?family=Shadows+Into+Light' rel='stylesheet' type='text/css'>

然后刷新浏览器缓存,就可以看到效果了

