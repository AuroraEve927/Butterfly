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

记录一个好看的主题[YunYouJun/hexo-theme-yun: ☁️ A fast & light & lovely theme for Hexo. 一个对可爱自以为是的 Hexo 主题。](https://github.com/YunYouJun/hexo-theme-yun)

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

4、音乐界面优化

[给你的博客加一个优雅的音乐界面 | 安知鱼 (anheyu.com)](https://blog.anheyu.com/posts/c3d3.html)

颜色配置路径source\css\var.styl；source\css\_global\index.styl

\#anMusic-page

 meting-js(id="12597348540" server="netease" type="playlist" mutex="true" preload="auto" theme="var(default-bg-color)" order="list")

安知鱼#425AEF

推荐#ad7a86

但是手机端的配置还有点问题

source\css\_layout\sidebar.styl

5、twikoo评论系统

[HEXO系列教程 | 在Butterfly主题中使用评论系统twikoo – 夜梦星尘の折腾日记 (yemengstar.com)](https://tech.yemengstar.com/hexo-tutorial-theme-butterfly-comments/)

[【docker】在服务器上安装docker/docker-compose – 夜梦星尘の折腾日记 (yemengstar.com)](https://tech.yemengstar.com/docker-install-docker-docker-compose-server/)

[【CentOS7】Linux安装Docker教程（保姆篇）_linux centos7 安装docker-CSDN博客](https://blog.csdn.net/Aaaaaaatwl/article/details/139860522)



[解决Docker在pull的时候报错Get https://registry-1.docker.io/v2/: net/http: request canceled (Client.Timeout e_docker login request canceled (client.timeout exce-CSDN博客](https://blog.csdn.net/Piconjo/article/details/105037514)

[彻底解决docker：docker: Get https://registry-1.docker.io/v2/: net/http: request canceled 报错-CSDN博客](https://blog.csdn.net/2301_79849395/article/details/142829852)

[目前国内可用Docker镜像源汇总（截至2024年8月） - CoderJia](https://www.coderjia.cn/archives/dba3f94c-a021-468a-8ac6-e840f85867ea)



```
version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '200:80'  # 冒号左边可以改成自己服务器未被占用的端口
      - '201:81'  # 冒号左边可以改成自己服务器未被占用的端口
      - '202:443' # 冒号左边可以改成自己服务器未被占用的端口
    volumes:
      - ./data:/data # 冒号左边可以改路径，现在是表示把数据存放在在当前文件夹下的 data 文件夹中
      - ./letsencrypt:/etc/letsencrypt  # 冒号左边可以改路径，现在是表示把数据存放在在当前文件夹下的 letsencrypt 文件夹中
```

http://106.54.2.126:201

[Login – Nginx Proxy Manager](http://106.54.2.126:201/login)

https://auroraeve.com:201



![image-20241013134447119](https://bu.dusays.com/2024/10/13/670b5e4ece54c.png)

[nginx-proxy-manager初次登录502 bad gateway_nginx proxy manager bad gateway-CSDN博客](https://blog.csdn.net/heroguo007/article/details/135225592)

[[解决了？从 2.9.19 更新到 2.10.4 后，本地端口 81 登录屏幕上出现“网关错误”，但网站仍可正常运行 ·问题 #3237 ·nginx代理管理器/nginx-proxy-manager (github.com)](https://github.com/NginxProxyManager/nginx-proxy-manager/issues/3237)

```
version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:latest'
    restart: unless-stopped
    ports:
      - '200:80'  # 冒号左边可以改成自己服务器未被占用的端口
      - '201:81'  # 冒号左边可以改成自己服务器未被占用的端口
      - '202:443' # 冒号左边可以改成自己服务器未被占用的端口
    environment:
      DB_MYSQL_HOST: "db"
      DB_MYSQL_PORT: 3306
      DB_MYSQL_USER: "npm"
      DB_MYSQL_PASSWORD: "(PASSWORD)"
      DB_MYSQL_NAME: "npm"
    volumes:
      - ./data:/data # 冒号左边可以改路径，现在是表示把数据存放在在当前文件夹下的 data 文件��中
      - ./letsencrypt:/etc/letsencrypt  # 冒号左边可以改路径，现在是表示把数据存放在在当前文件夹下的 letsencrypt 文件夹中
  db:
    image: 'jc21/mariadb-aria:latest'
    restart: unless-stopped
    environment:
      MYSQL_ROOT_PASSWORD: '(PASSWORD)'
      MYSQL_DATABASE: 'npm'
      MYSQL_USER: 'npm'
      MYSQL_PASSWORD: '(PASSWORD)'
    volumes:
      #- ./data/mysql:/var/lib/mysql
      - ./mysql:/var/lib/mysql
```

```
mkdir -p /root/data/docker_data/proxy
cd /root/data/docker_data/proxy
vim docker-compose.yml


version: '3'
services:
  app:
    image: 'jc21/nginx-proxy-manager:2.9.18'
    restart: unless-stopped
    ports:
      - '8881:80'
      - '81:81'
      - '4483:443'
    volumes:
      - ./data:/data 
      - ./letsencrypt:/etc/letsencrypt  
      
docker-compose pull
docker-compose up -d
```

6、安知鱼关于界面

[butterfly魔改关于页面 | 安知鱼](https://blog.anheyu.com/posts/e62b.html)

7、sitemap

[hexojs/hexo-generator-sitemap： Hexo 的站点地图生成器。](https://github.com/hexojs/hexo-generator-sitemap?tab=readme-ov-file)

官网上的配置文件有点问题，这是我的配置文件

```yaml
sitemap:
  path: 
    - sitemap.xml
    - sitemap.txt
  template: ./node_modules/hexo-generator-sitemap/sitemap.xml
  template_txt: ./node_modules/hexo-generator-sitemap/sitemap.txt
  rel: false
  tags: true
  categories: true
```
