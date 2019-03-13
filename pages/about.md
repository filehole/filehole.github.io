---
layout: page
title: About
description: 技术可能不能改变世界，但可以改变我
keywords: 文件洞, filehole
comments: true
menu: 关于
permalink: /about/
---

严小言要努力。

仰慕「优雅的艺术」，包含打码。

技术可能不能改变世界，但可以改变我。

## 联系

{% for website in site.data.social %}
* {{ website.sitename }}：[@{{ website.name }}]({{ website.url }})
{% endfor %}

## Skill Keywords

{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
