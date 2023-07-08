---
title: Notes笔记模块
excerpt: false
date: 2023-07-08 09:39:48
tags: [笔记,提示]
categories: 文章测试
thumbnail: ../images/Notes笔记模块/Fzd4vAIXgAEQrgj.jpg
cover:
---

#

### 大号提示块

#### 格式：

（`notel` 意思是 `note large` ，方便记，也可以写成 `note-large` ）

```
{% notel [颜色] [可选: 自定义图标] [标题] %}
内容
支持换行
{% endnotel %} 
```



| 参数       | 说明               | 可选值                                                       |
| ---------- | ------------------ | ------------------------------------------------------------ |
| 颜色       | 提示块的样式或颜色 | `blue` `red` `cyan` `purple` `orange` `yellow` `green`等颜色 |
| 自定义图标 | 自定义图标，选填   | [Fontawsome(opens in a new tab)](https://fontawesome.com/search) 的图标名称后半部分，比如 `fa-image` |

#### 例如：

```
{% notel default fa-info 信息 %}
换行测试
换行测试
换行测试
{% endnotel %}

{% notel blue 提示 %}
换行测试
换行测试
换行测试
{% endnotel %}

{% notel red 自定义标题 %}
换行测试
换行测试
换行测试
{% endnotel %} 
```

#### 效果：

{% notel default fa-info 信息 %}
换行测试
换行测试
换行测试
{% endnotel %}

{% notel blue 提示 %}
换行测试
换行测试
换行测试
{% endnotel %}

{% notel red 自定义标题 %}
换行测试
换行测试
换行测试
{% endnotel %} 

### 小号提示块

#### 格式：

```
{% note [样式/颜色] [可选: 自定义图标] %}
笔记内容
{% endnote %}
```



| 参数       | 说明               | 可选值                                                       |
| ---------- | ------------------ | :----------------------------------------------------------- |
| 样式/ 颜色 | 提示块的样式或颜色 | `success` `default` `primary` `info` `warning` `danger` `tip` `question` 以及 `blue` `red` `cyan` `purple` `orange` `yellow` `green`等颜色 |
| 自定义图标 | 自定义图标，选填   | [Fontawsome(opens in a new tab)](https://fontawesome.com/search) 的图标名称后半部分，比如 `fa-image` |

#### 例如：

```
{% note  %}
默认 提示块标签
{% endnote %}

{% note default  %}
default 提示块标签
{% endnote %}

{% note primary  %}
primary 提示块标签
{% endnote %} 

{% note success  %}
success 提示块标签
{% endnote %}

{% note info  %}
info 提示块标签
{% endnote %}

{% note warning  %}
warning 提示块标签
{% endnote %}

{% note danger  %}
danger 提示块标签
{% endnote %}

{% note red fa-bolt%}
自定义提示块标签
{% endnote %}
```

#### 效果：

{% note  %}
默认 提示块标签
{% endnote %}

{% note default  %}
default 提示块标签
{% endnote %}

{% note primary  %}
primary 提示块标签
{% endnote %} 

{% note success  %}
success 提示块标签
{% endnote %}

{% note info  %}
info 提示块标签
{% endnote %}

{% note warning  %}
warning 提示块标签
{% endnote %}

{% note danger  %}
danger 提示块标签
{% endnote %}

{% note red fa-bolt%}
自定义提示块标签
{% endnote %}