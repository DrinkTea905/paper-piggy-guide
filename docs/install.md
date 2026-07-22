---
layout: default
title: 安装与首次启动
kicker: 第 2 章
description: 安装 Windows 版 PaperPiggy，完成模型准备，并选好适合自己的隐私与 AI 模式。
last_reviewed: 2026-07-22
---

## 1. 下载正确的安装器

从 [GitHub Releases 最新版本](https://github.com/DrinkTea905/paper-piggy/releases/latest) 下载 Windows 安装器。项目目前正式分发的是 Windows 安装器；macOS 用户请参考主仓库中的源码运行说明。

<div class="callout warn">
  只从 PaperPiggy 官方 GitHub 仓库下载。不要从来历不明的网盘、软件站或聊天附件安装。
</div>

## 2. 选择安装位置

PaperPiggy 的程序、模型、索引和个人知识数据会放在同一个 PaperPiggy 文件夹体系内。建议选择：

- 空间充足的磁盘；
- 你有正常读写权限的位置；
- 不会被系统清理工具自动删除的位置。

不建议放进 Windows 的 Program Files；如果准备建立大型知识库，也不建议放在会频繁同步的网盘目录。

<div class="shot">安装器中的目录选择与空间提示</div>

## 3. 第一次启动与模型

首次启动会检查本地模型。如果模型缺失，应用会引导下载。模型用于本地语义检索和重排，下载量约 1 GB，具体以界面为准。

- 下载慢时先耐心等待；
- 不要同时启动多个 PaperPiggy；
- 下载失败可重试，已有数据不会因此被清空；
- 国内网络访问 GitHub 可能较慢。

<div class="shot">模型检查、下载进度与完成状态</div>

## 4. 选择知识库来源

首次向导会让你选择来源：

| 来源 | 适合谁 | 特点 |
|---|---|---|
| Zotero | 已用 Zotero 管理论文 | 能读取题录、附件和文库结构 |
| 普通文件夹 | 文献直接放在文件夹中 | 上手直观，适合小型或独立资料库 |

以后仍可在设置中调整。初次使用建议先选一个来源跑通，不要同时搬动大量文献。

## 5. 理解“本地”和“API”

PaperPiggy 的资料库和索引保存在本机。不同功能对外部服务的依赖不同：

- **本地检索**：语义检索和重排可使用本地模型。
- **在线 AI 功能**：对话、部分摘要或其他生成能力需要你配置的 API。
- **发送范围**：使用在线功能时，完成任务所需的查询与片段可能发送给对应服务商。

<div class="callout tip">
  如果文献敏感，先只用本地检索；决定启用在线功能前，了解所在机构的资料与合规要求。
</div>

## 6. 首页的新手指引

首次配置完成后会进入首页。首页的小猪头像是内置新手指引入口；它只在首页仪表盘出现。想复习时，回到首页点击头像即可。

<div class="shot">首页小猪头像与新手指引入口</div>

## 7. 安装完成检查

<ul class="checklist">
  <li>应用能正常打开，不会出现一闪而过的黑色终端窗口。</li>
  <li>模型状态显示可用。</li>
  <li>已选定 Zotero 或普通文件夹来源。</li>
  <li>知道 API Key 只应填写在应用设置中，不应出现在截图或公开问题里。</li>
</ul>

<div class="page-next">
  <a href="{{ '/quick-start.html' | relative_url }}">← 10 分钟快速开始</a>
  <a href="{{ '/library.html' | relative_url }}">下一章：建立知识库 →</a>
</div>
