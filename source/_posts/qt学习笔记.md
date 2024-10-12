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

项目——属性——常规——输出目录：..\Bin\

​			——调试——工作目录：..\Bin\

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

   
