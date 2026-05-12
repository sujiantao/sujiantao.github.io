+++
date = '2026-05-12T18:00:11+08:00'
draft = false
title = '在Arch Linux中使用rate-mirrors来寻找最佳镜像'
tags = ["archlinux","mirrors-list"]
categories = ["Dev"]
+++

## 为什么用rate-mirrors而不用传统的reflector

主要原因是Arch Linux是在台老机器上，由于硬件限制，有些软件无法更新到最新版本，导致reflector的依赖无法满足。

## 如何使用

> 安装rate-mirrors
> sudo pacman -S rate-mirrors
> 测试 Arch 镜像，并更新镜像列表
> rate-mirrors arch | sudo tee /etc/pacman.d/mirrorlist
