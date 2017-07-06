---
title: IDEA Ubuntu 中文乱码
date: 2017-07-06 11:40:38
tags: 
  - IDE
  - IDEA
  - Ubuntu
categories: 
  - Java
  - Tools
  - IDEA
---

引用地址 [http://blog.csdn.net/u013361445/article/details/51113692](http://blog.csdn.net/u013361445/article/details/51113692)

IDEA有分很多种乱码，菜单栏乱码，console输出中文乱码，代码乱码等等，以下提供一些解决方案。
### 设置里面的快捷键设置keymap出现中文，或者中文乱码
![](http://idiary.oss-cn-zhangjiakou.aliyuncs.com/images/20160410165135202.png)
**原因：**
IDEA里面的jdk选择的是本地的JDK，而JDK1.5以上的版本是由多国语言的，会选择操作系统的本地语言，所以编译的提示就会变成中文。
<!-- more --> 
**解决方案**
在 `IntelliJ IDEA 2016.1\bin\idea64.exe.vmoptions` 或 `IntelliJ IDEA 2016.1\bin\idea.exe.vmoptions` （根据你使用的版本决定）添加如下内容：
```
-Duser.country=EN
-Duser.language=us
```
### Console 输出乱码
**解决方案：**
在 `IntelliJ IDEA 2016.1\bin\idea64.exe.vmoptions` 或 `IntelliJ IDEA 2016.1\bin\idea.exe.vmoptions` 添加:
```
-Dfile.encoding=UTF-8
```
### 菜单乱码
![](http://idiary.oss-cn-zhangjiakou.aliyuncs.com/images/20160410165505735.png)
**原因:**
字体不支持中文的显示，在idea中，默认的是`ubuntu`字体，该字体并不支持中文显示，选择一个支持的字体 如`simsum`
![](http://idiary.oss-cn-zhangjiakou.aliyuncs.com/images/20160410165510547.png)