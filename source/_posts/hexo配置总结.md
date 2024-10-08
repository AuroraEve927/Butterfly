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

3、RSS功能

[Hexo butterfly 主题添加 RSS 插件 | 面具熊小屋 (maskbear.cn)](https://maskbear.cn/2023/05/12/Hexo_RSS插件配置/#:~:text=本文参考网上诸多教材)

[在butterfly主题中添加rss订阅 | 幻想の小窝 (mitpoppy.github.io)](https://mitpoppy.github.io/posts/fe13d434.html#:~:text=在butterfly)

~~hexo-abbrlink~~

~~可以把链接 permalink 转为数字的插件，配置容易，生成时自动转为数字。~~

~~hexo-generator-feed~~

~~生成 RSS 文件的插件~~

~~hexo-filter-nofollow~~

~~为网站使用到的所有外链添加rel="noopener external nofollow noreferrer", 可以有效地加强网站 SEO 和防止权重流失~~

~~hexo-generator-sitemap~~

~~生成 sitemap 的插件~~

~~hexo-generator-baidu-sitemap~~

~~看名字就知道，是专门为百度生成 sitemap 的插件~~

~~作者: Jerry~~
~~連結: https://butterfly.js.org/posts/4073eda/?highlight=rss~~
~~來源: Butterfly~~
~~版權屬於作者所有。商業用途請聯絡作者獲得授權，非商業用途請註明出處。~~

3、git push失败的情况

```cmd
git config --global -l
git config --global --unset http.proxy
git config --global --unset https.proxy
git config --global http.proxy "127.0.0.1:7890"
git config --global https.proxy "127.0.0.1:7890"
```

参考的这篇文章：[github fatal unable to access问题解决办法-电子发烧友网 (elecfans.com)](https://www.elecfans.com/d/2368032.html)
