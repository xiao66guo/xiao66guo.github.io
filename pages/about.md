---
layout: page
title: About
description: 不忘初心，方得始终
keywords: xiao 66 guo Bin, Sirius
comments: true
menu: 关于
permalink: /about/
---

iOS、Python Technical Develop Engineer。

Never give up on yourself, keep on going until you succeed!

永远都不要放弃自己，勇往直前，直至成功！

「 Sasuke 」粉丝☺

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
