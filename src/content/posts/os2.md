---
title: BUAA_OS 第二章 系统引导
published: 2026-07-08
description: 系统引导
image: ./images/cover1.jpg
tags: [OS]
category: 计算机课程
draft: false
---
# MIPS的基本地址空间

![地址空间划分](./images/image-11.avif)

**kseg1**是非cache存取的. **kseg1**是唯一在系统重启时能正常工作的地址空间

# 计算机的启动过程（MIPS）

## 第一阶段

CPU 会被硬件复位，然后从一个固定的启动地址开始取指令

对于很多 MIPS 系统，复位入口地址常见是：0xBFC00000

这个地址通常位于 **kseg1** 区域。

虚拟地址 0xBFC00000
对应物理地址 0x1FC00000

这个位置通常映射到 ROM、Flash 或者启动固件,执行Bootloader

## 第二阶段

Bootloader 加载内核

Bootloader 的任务是把操作系统内核放到内存里。

## 第三阶段

进入操作系统内核

进入内核后，系统还不能立刻运行用户程序。

## 第四阶段

内核初始化

## 第五阶段

调度并运行第一个进程

也就是从：操作系统内核代码

切换到：用户程序代码