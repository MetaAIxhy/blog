---
title: hexo和github.io页搭建博客回顾
date: 2016-05-11 22:24:40
tags: 代码
---

## 安装

整个过程还算比较顺利，因为之前用过git和reactNative for Android还有一些别东西，环境比较完善,没有遇到什么麻烦。

基本上参照这个网址上的来配置 http://www.jianshu.com/p/465830080ea9

就是最后运行hexo deploy命令的时候，什么都没有发生。搜索了一下，是因为_config.yml 最后的deploy配置那里，冒号后没有加空格造成的。

加上空格后，再运行就成功提交到git上了，这个功能集成的很不错。打开io页却发现页面没有正常加载。

打开控制台看加载的代码，原来我没有配置好_config.yml文件的root属性。

## 初步调整

themes文件夹下landscape就是默认的样式了,上网一搜，能用的样式还不少，看起来相当不错。

至于框架本身的实现，去node_modules里面看了一眼，比较复杂，突然好怀念python代码。

回到landscape文件夹看其实现，模板用的ejs,构建用grunt,css用stylus,大体上还是比较简单。

默认使用的是google的jQuery，无法加载。于是下载jQuery到\themes\landscape\source\js的文件夹内，去到\themes\landscape\layout\_partial的文件夹。把footer.ejs和after-footer.ejs的相应代码修改为引用内地的jQuery就ok了。

然后进入languages文件夹下修改了一下语言的翻译，今天就先这样吧。


