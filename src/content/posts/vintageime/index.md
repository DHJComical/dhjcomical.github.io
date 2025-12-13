---
title: IngameIME (1.12.2) - 彻底解决 MC 全屏输入法问题
published: 2024-03-20
description: "专为 Minecraft 1.12.2 打造的输入法优化模组，支持游戏内渲染选词框，彻底告别全屏下无法打字、选词框闪烁的烦恼。"
image: ""
tags: [Minecraft, Mod , 1.12.2, 1.7.10]
category: Minecraft Mod
draft: false
lang: zh
---

::github{repo="DHJComical/IngameIME-1.12.2"}

## 为什么需要这个模组？

对于还在坚守 **Minecraft 1.12.2** 版本的玩家来说，中文输入一直是一个痛点，尤其是在**全屏模式**下：

1.  **选词框消失**：打字时看不到候选词，只能“盲打”。
3.  **被迫窗口化**：为了聊天不得不退出全屏，沉浸感全无。

**IngameIME** 就是为了解决这些问题而生的。它通过 Mixin 游戏渲染，将输入法的候选词列表直接**渲染在游戏画面内部**，就像原生的 GUI 一样顺滑。 甚至支持 SmoothFont 这类修改文字渲染的Mod

:::tip
本项目是基于旧版开源代码的维护与优化版本，专注于 **1.12.2** 版本的稳定性和兼容性修复。
:::

## 核心功能

*   **📺 游戏内渲染**：候选词窗口不再浮在游戏窗口之外，而是作为游戏 UI 的一部分显示。
*   **🚀 全屏兼容**：完美支持全屏模式，不再需要盲目选词。
*   **⌨️ 多输入法支持**：兼容微软拼音、搜狗输入法等主流 IME。

## 安装指南

### 前置要求
*   **Minecraft 版本**：1.12.2 、1.7.10
*   **Mod Loader**：Minecraft Forge / Cleanroom
*   **Mod**：MixinBooter（1.12.2）、UniMixin（1.7.10）

### 相关链接
*   **[GitHub](https://github.com/DHJComical/IngameIME-1.12.2)**
*   **[CurseForge](https://www.curseforge.com/minecraft/mc-mods/ingameime-vintage)**
*   **[Modrinth](https://modrinth.com/mod/ingameime-vintage)**
*   **[MCMOD百科](https://www.mcmod.cn/class/20138.html)**

:::important[注意事项]
如果你安装了其他涉及输入法优化的模组（如 InputMethodBlocker 等），建议移除，以避免冲突。IngameIME 已经包含了必要的输入修复功能。
:::
