---
title: qt学习笔记
date: 2024-10-11 10:31:10
updated:
tags:
categories:
keywords:
description:
top_img:
comments:
cover:
---

# QT学习笔记

[1.VS下开发Qt应用环境搭建_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1Vt4y1n7us?spm_id_from=333.788.videopod.sections&vd_source=851eb39e369398dfd488218128ad07b6)

# 一些约定

软件环境版本号：VS2019；QT：5.13.2；opencv：3.4.0-vc14_vc15

项目——属性——常规——输出目录：..\Bin\

​			——调试——工作目录：..\Bin\

引入OpenCV库文件

QT预览Ctrl+R

# 主要函数

## Label

1. 显示汉字

   ```c++
   ui.labelPicture->setText(QString::fromLocal8Bit("Qt显示汉字"));
   ```

2. 显示图片

   ```c++
       //路径全英文
       QPixmap pixPic2show("D:\\myfile\\project\\Rubik-s-Cube-Robot\\source\\img\\111.jpg");
       ui.labelPicture->setPixmap(pixPic2show);
       //如果路径有中文
       QPixmap pixPic2show(QString::fromLocal8Bit("D:\\myfile\\project\\Rubik-s-Cube-Robot\\source\\img\\魔方背景.jpg"));
       ui.labelPicture->setPixmap(pixPic2show);
   
   //  beifen
       ui.labelPicture->setText(QString::fromLocal8Bit("Qt显示汉字"));
       QImage imgPic2show(QString::fromLocal8Bit("D:\\myfile\\project\\Rubik-s-Cube-Robot\\source\\img\\魔方背景.jpg"));   //引用图片
       auto sizelabelPicture = ui.labelPicture->size();
       imgPic2show=imgPic2show.scaled(ui.labelPicture->size(),Qt::KeepAspectRatio);    //固定宽高比
   
       QPixmap pixPic2show=QPixmap::fromImage(imgPic2show);    //转换格式
       ui.labelPicture->setPixmap(pixPic2show);       //显示图片
   ```

   

## Botton

[QT使用按钮打开新窗口_qt点击按钮弹出另一个界面-CSDN博客](https://blog.csdn.net/shenlaoli/article/details/128681032)

[QT---制作简易串口助手_qt编写串口助手-CSDN博客](https://blog.csdn.net/qq_58744641/article/details/128837479)

[Qt多界面使用串口收发数据_qt串口通信,数据发给其他多个类使用-CSDN博客](https://blog.csdn.net/weixin_43742616/article/details/113352522)

[qt 指示灯 状态灯 红绿灯 LED灯：使用QLabel实现_qt界面ui设计指示灯-CSDN博客](https://blog.csdn.net/Fourier_1024/article/details/113517982?utm_medium=distribute.pc_relevant.none-task-blog-2~default~baidujs_baidulandingword~default-0-113517982-blog-140586898.235^v43^pc_blog_bottom_relevance_base4&spm=1001.2101.3001.4242.1&utm_relevant_index=2)

[QT摄像头采集_qt摄像头采集数据-CSDN博客](https://blog.csdn.net/u011436603/article/details/136328306)

[QT中的摄像头拍摄保存画面_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV17BDvYaEDv/?vd_source=851eb39e369398dfd488218128ad07b6)

[用qt打开自己电脑摄像头并截屏摄像头图像。_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1iL4y1P78V/?vd_source=851eb39e369398dfd488218128ad07b6)
