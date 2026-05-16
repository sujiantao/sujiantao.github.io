+++
date = '2026-05-16T13:47:05+08:00'
draft = true
title = 'Pacman软件包管理器'
tags = ["Arch","ArchLinux", "Linux", "pacman"]
categories = ["Dev"]
+++

pacman软件包管理器是 Arch Linux 的主要特色之一。它将简单的二进制软件包格式与易于使用的 Arch 构建系统相结合。pacman的目标是让用户能够轻松管理软件包，无论这些软件包来自官方仓库还是用户自行构建的。

pacman通过与主服务器同步软件包列表来保持系统最新状态。这种服务器/客户端模式还允许用户仅需一条简单命令即可下载安装软件包，同时自动包含所有必需的依赖项。

pacman 采用 C 语言编写，并使用 bsdtar(1) tar 格式 进行打包。

>提示
>pacman 软件包包含 makepkg 和 vercmp(8) 等工具。其它有用的工具（如 pactree 和 checkupdates）则位于 pacman-contrib 软件包中。运行 pacman -Ql pacman pacman-contrib | grep -E 'bin/.+' 可查看完整列表。