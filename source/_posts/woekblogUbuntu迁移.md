---
title: woekblogUbuntu迁移
excerpt: false
date: 2026-03-06 11:14:39
tags:
categories:
thumbnail:
cover: 
---

Github clone workblog 到其他电脑本地，再发博客

1.从github zhw账户中clone仓库workblog到本地新建文件夹

ubuntu@ThinkBook:~/Documents/workUbuntu$ git clone git@github-zhw:zhw4616/workblog.git（会嵌套一层文件夹）
git clone git@github-zhw:zhw4616/workblog.git.（如果在git后面加点就直接clone不会嵌套一层文件夹）
#注意由于SSH key有两个，所以根据ssh config匹配相应key，git@github.com:zhw4616/workblog.git改为上述host：
执行完成：
Cloning into 'workblog'...
remote: Enumerating objects: 729, done.
remote: Counting objects: 100% (276/276), done.
remote: Compressing objects: 100% (222/222), done.
remote: Total 729 (delta 79), reused 224 (delta 34), pack-reused 453 (from 1)
Receiving objects: 100% (729/729), 53.96 MiB | 4.96 MiB/s, done.
Resolving deltas: 100% (214/214), done.

2.本地文件夹安装依赖，非常重要。因push到repo中的文件夹都含有.ignore并为推送全部文件

npm install
#此步操作要在workblog文件夹下，不然会npm报错，因为需要package json文件才能执行安装
不要使用sudo安装，会导致权限问题，后续操作会更麻烦

执行完成：
ubuntu@ThinkBook:~/Documents/workUbuntu/workblog$ npm install
npm warn deprecated cuid@2.1.8: Cuid and other k-sortable and non-cryptographic ids (Ulid, ObjectId, KSUID, all UUIDs) are all insecure. Use @paralleldrive/cuid2 instead.

added 245 packages, and audited 246 packages in 6s

23 packages are looking for funding
  run `npm fund` for details

24 vulnerabilities (10 low, 7 moderate, 6 high, 1 critical)

To address issues that do not require attention, run:
  npm audit fix

To address all issues (including breaking changes), run:
  npm audit fix --force

Run `npm audit` for details.

![](../images/woekblogUbuntu迁移/19ebbc51df7a89d1a51a306b4b91759c90f3c6e7.jpeg)
