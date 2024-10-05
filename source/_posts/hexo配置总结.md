---
title: hexo配置总结
date: 2024-10-05 11:29:43
top: 98
tags:
---

# 简介

这里总结了一些搭建博客时关于配置的问题。

[关于hexo配置汇总 | a.d博客 (aiheadn.cn)](https://blog.aiheadn.cn/archives/1b4c065d.html)

[Heo同款loading动画 | 安知鱼 (anheyu.com)](https://blog.anheyu.com/posts/52d8.html)

[Hexo安知鱼主题修改背景折腾记录 | GoodBoyboy 's Blog｜惬意小屋-点滴记忆](https://blog.goodboyboy.top/posts/3299842545.html#:~:text=当完成上面操作后我们)

1、添加--anzhiyu-card-bg

主题文件夹下\source\css\_global\index.styl

添加

```
:root
  --anzhiyu-card-bg: #fff;
```

2、作者链接修改：

在themes\butterfly\_config.yml

```yaml
post_copyright:
  enable: true
  decode: false
  author_href: https://blog.auroraeve.com/
  license: CC BY-NC-SA 4.0
  license_url: https://creativecommons.org/licenses/by-nc-sa/4.0/
```

author_href: https://blog.auroraeve.com/（你的主页链接）

接着修改文章链接

在_config.yml里

```
# URL
## Set your site url here. For example, if you use GitHub Page, set url as 'https://username.github.io/project'
url: http://example.com
permalink: :year/:month/:day/:title/
permalink_defaults:
pretty_urls:
  trailing_index: true # Set to false to remove trailing 'index.html' from permalinks
  trailing_html: true # Set to false to remove trailing '.html' from permalinks
```

url: http://example.com（修改为你的主页链接）
