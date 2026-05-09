+++
date = '2026-05-02T22:11:43+08:00'
draft = false
title = 'source命令'
tags = ["shell"]
categories = ["工作"]
+++  
在 shell 环境中，source 是一个非常核心的内置命令。
简单来说，它的作用是：在当前正在运行的 Shell 会话中执行指定文件中的脚本。

## 1. 核心功能

通常情况下，如果你直接运行一个脚本（如 ./script.sh），系统会启动一个子进程（Subshell）来执行它。脚本执行完后，子进程关闭，脚本中定义的变量或更改的环境变量都会随之消失。  
而使用 source：  
它不会创建子进程，而是在当前进程中逐行执行代码。
脚本中所有的变量赋值、别名（alias）和函数都会保留在当前的终端会话中。

## 2. 常见用法

在 Arch Linux 或任何 Linux 发行版中，你最常遇到它的场景就是更新配置文件。
刷新配置文件

当你修改了 ~/.zshrc（或 .bashrc）后，为了让配置立即生效而不用关闭并重新打开终端，你会执行：

    Bash

    source ~/.zshrc

或者使用它的缩写（一个点号）：

    Bash

    . ~/.zshrc

>[!INFO]注意：
>. 和 source 在绝大多数 shell（如 bash, zsh）中是完全等价的。

激活虚拟环境

在 Python 开发中，激活环境本质上就是通过 source 修改当前的 PATH 变量：

    Bash

    source .venv/bin/activate

## 3. source vs sh/./ 的区别

| 特性 | source script.sh | ./script.sh 或 sh script.sh |
| :---: | :--- | :--- |
| 执行环境 | 当前 Shell 进程 | 新开一个 Shell 进程 |
| 变量影响 | 脚本内的变量会留在当前终端 | 脚本运行完变量立刻销毁 |
| 权限要求 | 只需要文件的读取权限 | 必须拥有执行权限（chmod +x） |
| 典型用途 | 加载配置，切换环境，定义函数 | 独立工具或自动化任务 |
