---
title: Windows11系统yt-dlp安装与使用
excerpt: false
date: 2026-02-06 10:09:25
tags: 
categories:
thumbnail:
cover: ../images/Windows11%E7%B3%BB%E7%BB%9Fyt-dlp%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8/9mmYDgZ3CtyVPqmKqin3hN-1070-80.png.webp

---

这是一份为您整理的 **Windows 11 安装与使用 yt-dlp 完整指南**。

------

# Windows 11 下 yt-dlp 安装与高级使用指南

[yt-dlp](https://github.com/yt-dlp/yt-dlp) 是目前最强大的命令行视频下载工具，支持 YouTube、Bilibili 等数千个网站。本文将带你从零开始完成配置，并解决常见的 Cookie 加密和验证码问题。

## 一、 安装步骤

在 Windows 11 上，推荐使用系统自带的包管理器 `winget` 进行安装，这样可以自动配置环境变量。

### 1. 安装本体

以管理员身份打开 **终端 (PowerShell)**，运行：

PowerShell

```
winget install yt-dlp
```

### 2. 安装核心组件 FFmpeg (必选)

**注意：** 如果不安装 FFmpeg，yt-dlp 将无法下载 1080P 以上的高清视频，也无法合并音视频流。

PowerShell

```
winget install ffmpeg
```

### 3. 生效配置

安装完成后，**必须关闭并重新打开终端窗口**，系统才能识别 `yt-dlp` 指令。你可以通过输入 `yt-dlp --version` 来验证是否安装成功。

------

## 二、 基础使用方法

打开终端，进入你想保存视频的文件夹，使用以下命令：

- **默认最高画质下载：**

  PowerShell

  ```
  yt-dlp "视频链接"
  ```

- **查看所有可用画质：**

  在下载之前，建议先查看该视频支持哪些格式和分辨率：

  PowerShell

  ```
  yt-dlp -F "视频链接"
  ```

  运行后你会看到一个列表，每一行开头都有一个 **ID（格式代码）**，比如 `248`, `137` 等。

- **下载特定画质：**

  如果你已经通过上面的命令找到了心仪的 ID（比如视频 ID 是 `137`，音频 ID 是 `140`），可以使用 `-f` 参数下载：

  PowerShell

  ```
  yt-dlp -f 137+140 "视频链接"
  ```

  *注意：中间用 `+` 号连接表示将选定的视频和音频合并（需要安装 FFmpeg）。*

- **下载特定分辨率 (如 1080p)：**

  PowerShell

  ```
  yt-dlp -f "bestvideo[height<=1080]+bestaudio/best" "视频链接"
  ```

- **仅下载音频并转为 MP3：**

  PowerShell

  ```
  yt-dlp -x --audio-format mp3 "视频链接"
  ```

------

## 三、 进阶：处理“机器人验证”与“Cookie 报错”

当你遇到 `Sign in to confirm you’re not a bot` 或 `Failed to decrypt with DPAPI` 错误时，说明平台限制了匿名下载。

### 方法 A：直接从浏览器调用（首选）

yt-dlp 可以尝试直接读取浏览器的登录状态。

> **注意：** 运行命令前请先关闭对应的浏览器窗口。

PowerShell

```
# 使用 Edge 浏览器的登录信息
yt-dlp --cookies-from-browser edge "视频链接"

# 使用 Chrome 浏览器的登录信息
yt-dlp --cookies-from-browser chrome "视频链接"
```

### 方法 B：使用 Cookie 导出插件（最稳定）

如果直接读取报错（如 DPAPI 加密错误），请按以下步骤操作：

1. 在浏览器安装 **Get-cookies.txt** 扩展插件。

2. 登录视频网站，使用插件将 Cookie 导出为 `cookies.txt`。

3. 将该文件放入下载文件夹，执行：

   **查看所有可用画质：**插件下载的cookies文件www.youtube.com_cookies.txt存放在你要存放下载视频的文件夹中

   PowerShell 

   ```
    yt-dlp -F --cookies www.youtube.com_cookies.txt "视频链接"
   ```

   其他命令加入cookies文档后执行，比如

   PowerShell

   ```
   yt-dlp -f 137+140 --cookies www.youtube.com_cookies.txt "视频链接"
   ```

------

## 

------

## 四、 常见问题排查 (FAQ)

| **问题现象**                     | **原因分析**        | **解决方案**                         |
| -------------------------------- | ------------------- | ------------------------------------ |
| **提示无法识别 "yt-dlp"**        | 环境变量未生效      | 重启终端窗口；或检查是否安装成功     |
| **下载的视频没有声音**           | 缺少 FFmpeg         | 运行 `winget install ffmpeg`         |
| **无法下载最高画质**             | 未登录或未传 Cookie | 使用 `--cookies-from-browser` 参数   |
| **提示 Could not copy database** | 浏览器正在运行      | 关闭浏览器所有进程后再试             |
| **提示 DPAPI 解密失败**          | 系统权限或加密限制  | 尝试使用“方法 B”手动导出 Cookie 文件 |

------

## 五、 常用维护命令

为了应对视频网站的策略变化，建议定期更新工具：

- **更新 yt-dlp：** `yt-dlp -U`
- **更新 FFmpeg：** `winget upgrade ffmpeg`

------

![](../images/Windows11%E7%B3%BB%E7%BB%9Fyt-dlp%E5%AE%89%E8%A3%85%E4%B8%8E%E4%BD%BF%E7%94%A8/9mmYDgZ3CtyVPqmKqin3hN-1070-80.png.webp)