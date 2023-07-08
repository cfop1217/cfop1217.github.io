---
title: 修改scaffold
excerpt: false
date: 2023-06-06 09:40:26
tags: [文章默认项,图片显示,categories问题]
categories: hexo
thumbnail: /images/blog/wallhaven-wqery6-light.webp
cover: 
---

#

#### 修改新建文章默认项

hexo new 新文章，文章页的front matter中只有titile，date，tags三项内容，一般情况下新建文章包含首页缩略图，文章页头图，不希望出现文章摘要信息。

![](../images/修改scaffold/Screenshot.png)

通过修改根目录下scaffold文件夹下post.md文件，修改默认文章页front matter内容，添加所需要项目，如thumbnail文章首页缩略图，文章页头图cover，摘要excerpt不显示或者修改摘要内容。

#### 图片本地无法正常显示

PS：文章插入图片又出现hexo s本地无法显示的情况，昨天也是某种图片无法加载，具体原因不详，初步发现是图片名称格式或内容的问题，修改图片名称为相对简单的名称后，即可正常加载。如Screenshot 2023-06-06 094854.png无法加载，修改为Screenshot.png即可正常加载显示。

#### 添加categories网页不更新

添加categories时，通过每篇文章独立加入，修改上述文件，添加categories：项，新建文章就好增加categories项，每次编辑文章进行分类。实际操作中，每篇文章添加categories后，hexo g-s-d，本地显示正常，推送网页并没有更新，至少一个小时后仍未有更新。本地命令hexo cl后，再hexo-g-s-d本地正常，推送后延迟5分钟左右，网页正常更新，添加了categories项目。