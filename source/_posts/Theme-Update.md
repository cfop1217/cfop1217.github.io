---
title: Theme Update
excerpt: false
date: 2023-06-26 15:15:30
tags: ThemeUpdate
categories: hexo
thumbnail: ../images/Theme-Update/47690335362.jpeg
cover: 
---

### 2023.06.26 Theme Update

```
$ npm install hexo-theme-redefine@latest 
```

current version is v2.2.1,latest version is v2.2.1

手动修改了部分配置文件，对网页使用没有影响。字体和大小有少许改动，更新了字体样式，网页字体已更新。字体更新有延迟，需要命令hexo cl后再hexo g重新生成，hexo d推送网站后，字体更新成功，这样操作后字体感觉也是有延迟的，推送后过了一段时间网页才更新新字体。

一开始升级主题成功后，网页字体并没有更改，不知道什么原因，于是采取上面步骤，字体更新成功。不确定是延迟还是需要clean后才能更新字体。

目前是正常使用该主题，主题配置文件设置基本清楚，但是其他的文件内部关联并不清楚，比如网页配置、设置参数等。

![](../images/Theme-Update/47690335362.jpeg)

PS：添加categories时也出现了网页无法更新的问题，使用hexo cl命令后才延迟5分钟左右正常更新。看来这种变动，还是需要提前clean一下，重新推送。