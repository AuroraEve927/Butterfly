---
title: 优雅地在word中插入代码块
date: 2024-06-12 18:29:46
tags:
  - 代码块
categories:
  - 教程
top_img: 
cover: 
---

# 优雅地在word中插入代码块

> 在word中插入代码块一直都是一个让人很头疼的问题。
> 我们常见的代码块一直存在于csdn中，他在写文章的页面就会自带代码块功能，但是在word这边是没有的。
> 我之前一直常用的格式转化网站是http://word.wd1x.com/
> 本帖旨在汇总常见的代码块实现方法：
> 参考文献如下：
> [代码如何优雅地嵌入word中_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1nU4y187FY/?spm_id_from=333.337.search-card.all.click&vd_source=851eb39e369398dfd488218128ad07b6)

# 方法一：网站自动生成

我搜集了3个好用的转换网站。这三个网站的转换后的格式都一样的大家不必纠结用哪个都行。

1. Word/PPT代码在线高亮：http://word.wd1x.com/
   这个是我一直在用的
   ![image-20240612185546808](https://bu.dusays.com/2024/06/12/66697eb37aae3.png)
2. CodeInWord：http://www.codeinword.com/
   UP主推荐的
   ![image-20240612185422588](https://bu.dusays.com/2024/06/12/66697e6680e8c.png)
3. 代码在线高亮工具：https://highlightcode.com/
   留作备用
   ![image-20240612185730758](https://bu.dusays.com/2024/06/12/66697f1b73349.png)
4. Carbon：https://carbon.now.sh/
   生成的是图片，不是代码块。但是效果很好。
   ![image-20240612190004716](https://bu.dusays.com/2024/06/12/66697fb57ca30.png)

---

小结：可以看出前两个网址的格式是完全一致的、第三个网址比前两个多了一些细节，但基本大差不差。
第四个是生成图片，效果还不错的。
这些链接已经被收藏到：`清单`——`宝藏网站`页面中大家可以很方便得找到它。

# 方法二：VSCode

直接VSCode：Ctrl+C && Ctrl+V

# 方法三：Word“宏”+格式修改

详见视频：[代码如何优雅地嵌入word中_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1nU4y187FY/?spm_id_from=333.337.search-card.all.click&vd_source=851eb39e369398dfd488218128ad07b6)

宏：本质上就是添加了一个只保留文本粘贴得快捷键：Ctrl+B

格式：给代码块加上底纹，视频中所用的是灰色。

![image-20240612192501326](https://bu.dusays.com/2024/06/12/6669858e01808.png)

# 方法四：NotePad--（暂不可用）

软件安装网站：https://gitee.com/cxasm/notepad--；https://github.com/cxasm/notepad--

视频教程：[怎样在Word中插入高亮代码？快速在Word文档插入代码块方法分享︱计算机论文排版加分项_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1of4y1r76g/?spm_id_from=333.337.search-card.all.click&vd_source=851eb39e369398dfd488218128ad07b6)

现在碰到的问题是notepad--无法复制样式，还需更新。

# 总结

本文列举了几种word中插入代码块的方法。

比较实用的方法有2种：网页转换和设置底纹

推荐排序：网页转换>格式修改>VSCode>Notepad--

---

最后，附上本文实例代码：代码源于菜鸟教程

```c
#include <stdio.h>
 
int main ()
{
    int var_runoob = 10;
    int *p;              // 定义指针变量
    p = &var_runoob;
 
   printf("var_runoob 变量的地址： %p\n", p);
   return 0;
}
```

