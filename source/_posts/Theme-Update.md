---
title: Theme Update
excerpt: false
date: 2023-06-26 15:15:30
tags: [redefine,themeupdate]
categories: hexo
thumbnail: ../images/Theme-Update/47690335362.jpeg
cover: 
---



### Redefine Theme Update 2023.06.05

```
$ cd your-hexo-site
$ npm install hexo-theme-redefine@latest
```

根目录下执行该命令即可更新redefine主题，主题文件夹位于..\node_modules\hexo-theme-redefine

#### 更新覆盖

更新后，主题文件夹（..\node_modules\hexo-theme-redefine）全部覆盖更新，之前设定的网页相关图片全部丢失，所以主题文件夹中尽量不要有什么改动，因为更新时会被全部覆盖。目前也没有其他方面的改动，主要是网页图标的变动。

#### 网页图片地址变更

将网页图标文件从主题文件夹转移出来，放在根目录\source\images\blog picture

修改_config.redefine.yml文件中图片引用地址\images\blog picture\ 图片名字。

这样主题更新后不会影响网页图片加载。



### Redefine Theme Update 2023.06.26 

```
$ npm install hexo-theme-redefine@latest 
```

current version is v2.2.1,latest version is v2.2.1

手动修改了部分配置文件，对网页使用没有影响。字体和大小有少许改动，更新了字体样式，网页字体已更新。字体更新有延迟，需要命令hexo cl后再hexo g重新生成，hexo d推送网站后，字体更新成功，这样操作后字体感觉也是有延迟的，推送后过了一段时间网页才更新新字体。

一开始升级主题成功后，网页字体并没有更改，不知道什么原因，于是采取上面步骤，字体更新成功。不确定是延迟还是需要clean后才能更新字体。

目前是正常使用该主题，主题配置文件设置基本清楚，但是其他的文件内部关联并不清楚，比如网页配置、设置参数等。

![](../images/Theme-Update/47690335362.jpeg)

**PS：**添加categories时也出现了网页无法更新的问题，使用hexo cl命令后才延迟5分钟左右正常更新。看来这种变动，还是需要提前clean一下，重新推送。

#### 应用子仓库主题更新问题

如果将该主题应用于子仓库，主题文件夹下好几个文件需要改动，如果升级主题会全部覆盖，所以需要将修改的主题文件夹hexo-theme-redefine拷贝到根目录theme中，改名redefine，在此改动，升级后该文件夹不被覆盖。



