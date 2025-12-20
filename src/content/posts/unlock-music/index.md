---
title: Unlock Music - 浏览器端的音乐加密格式解锁工具
published: 2025-12-20
description: "基于 React 重构的音乐解锁工具，支持 QMC、NCM、KWM 等主流加密格式。纯前端解密，保护隐私，无需上传文件。"
image: ""
tags: [Tools, Music]
category: 实用项目
draft: false
lang: zh
---

::github{repo="DHJComical/um-react-mirror"}

## 项目介绍

**Unlock Music (React)** 是一个在浏览器中运行的加密音乐文件解锁工具。

很多时候，我们在各大音乐平台下载的音乐文件是加密格式（如 `.ncm`, `.qmc`, `.mflac` 等），导致无法在其他播放器或设备上播放。这个工具的初衷就是为了方便用户将自己已购的音乐转换为通用的 MP3 或 FLAC 格式。

本项目是原 [Unlock Music (Vue)](https://git.um-react.app/um/web) 项目的 **React 重构版本**，使用了更现代的技术栈（React + Vite + Rust/Wasm），性能更强，体验更好。

:::tip
本站部署的是该项目的镜像版本，你可以直接访问我的部署地址使用，也可以查看源码自行部署。（GitHub Pages请使用gh-action分支且在Settings里将发布来源设置为Actions）
:::

## 核心特性

*   **🛡️ 隐私安全**：所有解密过程都在浏览器本地（Web Worker）完成，**不会上传任何文件**到服务器，确保你的数据安全。
*   **🚀 性能强大**：引入了 Rust 编写的解密库 (`@unlock-music/crypto`)，配合 WebAssembly 技术，解密速度极快。
*   **📱 离线可用**：支持 PWA（渐进式 Web 应用），安装后即使没有网络也能使用。
*   **📂 批量处理**：支持拖拽上传，可以一次性解锁大量文件。

## 支持的格式

目前支持绝大多数主流平台的加密格式：

*   **QQ 音乐**:
    *   QMCv1 (`.qmc3`, `.qmcflac`)
    *   QMCv2 PC/Android/iOS 端 (`.mflac`, `.mgg`, `.mflac0` 等)
*   **网易云音乐**: `.ncm`
*   **酷我音乐**: `.kwm`, `.mflac`
*   **酷狗音乐**: `.kgm`, `.vpr`, `.kgg`
*   **虾米音乐**: `.xm`
*   **其他**: 喜马拉雅 (`.x2m`), 咪咕 (`.mg3d`), 蜻蜓FM (`.qta`) 等

:::warning
部分较新的加密格式（如新版 QQ 音乐、酷我、酷狗的高音质文件）需要配合 **密钥数据库** 使用。你需要自行提取设备密钥并导入到设置中才能解锁。
:::

## 如何使用

1.  访问 [**在线解锁工具**](https://dhjcomical.github.io/um-react-mirror/)（也就是本站部署的版本）。
2.  将你的加密音乐文件**拖拽**到网页中间的区域。
3.  等待解密完成。
4.  点击下载转换后的文件。

## 技术细节

如果你对技术感兴趣，这个项目也是一个很好的 React 学习案例：

*   **架构**：主线程负责 UI 渲染，**Web Worker** 负责繁重的解密计算，避免页面卡顿。
*   **数据传输**：主线程生成 Blob URL，通过 `postMessage` 传递给 Worker，Worker 再通过 `fetch` API 获取数据。
*   **部署**：本项目无法直接运行在子目录下，需要配置 `base` 路径和 `HashRouter`（这也是我之前折腾部署遇到的主要坑，现已修复）。

## 相关链接

*   **官方仓库**: [https://git.um-react.app/um/um-react](https://git.um-react.app/um/um-react)
*   **Telegram 群组**: [`@unlock_music_chat`](https://t.me/unlock_music_chat)
*   **CLI 版本**: 如果你有成千上万个文件需要处理，建议使用 [CLI 版本](https://git.um-react.app/um/cli)。

---

> **免责声明**：本项目仅供技术研究和学习使用。请支持正版音乐，修改、再分发时请遵循项目的授权协议。