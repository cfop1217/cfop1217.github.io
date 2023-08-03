---
title: Hexo安装使用
date: 2023-06-02 19:55:03
tags: 安装
categories: hexo
thumbnail: ../images/hexo安装使用/wallhaven-wqery6-light.webp
cover: 
---

#

### 安装

安装 Hexo 只需几分钟时间。

#### 安装前提

安装 Hexo 相当简单，只需要先安装下列应用程序即可：

- [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
- [Git](http://git-scm.com/)

如果您的电脑中尚未安装所需要的程序，请根据以下安装指示完成安装。

#### 安装 Git

- Windows：下载并安装 [git](https://git-scm.com/download/win).

#### 安装 Node.js

Node.js 为大多数平台提供了官方的 [安装程序](https://nodejs.org/zh-cn/download/)。使用 Node.js 官方安装程序时，请确保勾选 **Add to PATH** 选项（默认已勾选）。

#### 安装 Hexo

所有必备的应用程序安装完成后，即可使用 npm 安装 Hexo。

```
$ npm install -g hexo-cli
```

安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。

```
$ hexo init <folder>
$ cd <folder>
$ npm install
```

可以直接建立blog文件夹，在文件夹使用git bash操作命令

```
$ hexo init
$ npm install
```

新建完成后，指定文件夹的目录如下：

```
.
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _drafts
|   └── _posts
└── themes
```

#### _config.yml

网站的 [配置](https://hexo.io/zh-cn/docs/configuration) 信息，您可以在此配置大部分的参数。

### 服务器

#### [hexo-server](https://github.com/hexojs/hexo-server)

Hexo 3.0 把服务器独立成了个别模块，您必须先安装 [hexo-server](https://github.com/hexojs/hexo-server) 才能使用。

```
$ npm install hexo-server --save
```

安装完成后，输入以下命令以启动服务器，您的网站会在 `http://localhost:4000` 下启动。在服务器启动期间，Hexo 会监视文件变动并自动更新，您无须重启服务器。

```
$ hexo server
```

如果您想要更改端口，或是在执行时遇到了 `EADDRINUSE` 错误，可以在执行时使用 `-p` 选项指定其他端口，如下：

```
$ hexo server -p 5000
```

#### 静态模式

在静态模式下，服务器只处理 `public` 文件夹内的文件，而不会处理文件变动，在执行时，您应该先自行执行 `hexo generate`，此模式通常用于生产环境（production mode）下。

```
$ hexo server -s
```

### 生成文件

使用 Hexo 生成静态文件快速而且简单。

```
$ hexo generate
```

#### 监视文件变动

Hexo 能够监视文件变动并立即重新生成静态文件，在生成时会比对文件的 SHA1 checksum，只有变动的文件才会写入。

```
$ hexo generate --watch
```

#### 完成后部署

您可执行下列的其中一个命令，让 Hexo 在生成完毕后自动部署网站，两个命令的作用是相同的。

```
$ hexo generate --deploy
$ hexo deploy --generate
```

### GitHub Pages 一键部署

以下教学改编自 [一键部署](https://hexo.io/zh-cn/docs/one-command-deployment)。

1. 安装 [hexo-deployer-git](https://github.com/hexojs/hexo-deployer-git)。Installation

   ```
   $ npm install hexo-deployer-git --save
   ```

2. 在 `_config.yml` 中添加以下配置（如果配置已经存在，请将其替换为如下）:

```
deploy:
  type: git
  repo: git仓库SHH地址 
  branch: main
```

此部分需要前期工作先设置github的SHH登录，生成SHH密钥，添加到github后方可使用。具体设置可以参考GitHub帮助文档。

[SHH帮助文档]: https://docs.github.com/zh/authentication/connecting-to-github-with-ssh/about-ssh

执行 `hexo clean && hexo deploy` 。

浏览 `<GitHub 用户名>.github.io` 检查你的网站能否运作。

### 帮助文档

[Hexo文档]: https://hexo.io/zh-cn/docs/
[GItHub文档]: https://docs.github.com/zh
[Redefine主题文档]: https://redefine-docs.ohevan.com/



