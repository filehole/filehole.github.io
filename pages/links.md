---
layout: page
title: Links
description: 没有链接的博客是孤独的
keywords: 友情链接
comments: true
menu: 链接
permalink: /links/
---

> 我的宿命分为两段，
> 未遇见你时，和遇见你以后。
> 你治好我的忧郁，而后赐我悲伤。
> 忧郁和悲伤之间的片刻欢喜，透支了我生命全部的热情储蓄。
> 想饮一些酒，让灵魂失重，好被风吹走。
> 可一想到终将是你的路人，便觉得，沦为整个世界的路人。
> 风虽大，都绕过我灵魂。

{% for link in site.data.links %}
* [{{ link.name }}]({{ link.url }})
{% endfor %}
