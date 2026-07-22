---
layout: default
title: 安装与配置 API
kicker: 第 2 章 · 基础设置
description: 安装 PaperPiggy，并把硅基流动配置成默认检索引擎。
last_reviewed: 2026-07-22
---

## 下载与安装

从 [PaperPiggy Releases](https://github.com/DrinkTea905/paper-piggy/releases/latest) 下载最新的 Windows 安装器。当前正式分发的是 Windows 版本；macOS 暂时只能从源码运行。

安装时建议选择：

- 空间充足的磁盘；
- 自己有正常读写权限的位置；
- 不会被系统清理软件自动清理的位置。

PaperPiggy 的应用、索引、模型和 Agent 工作区会集中在同一套数据目录中，日后迁移和备份更清楚。

## 为什么主教程使用 API 模式

PaperPiggy 的检索不只是把问题发给一个聊天模型。它还需要：

- **嵌入模型**：把问题和文献转换成可比较的语义向量；
- **重排模型**：把候选结果重新排序，提高相关性；
- **大语言模型**：用于部分摘要、题录抽取或应用内对话。

硅基流动同时提供 PaperPiggy 已配置好的嵌入和重排模型，而且这两个模型可以免费调用。因此，本教程统一采用“硅基流动 + API 模式”。

DeepSeek、Kimi 等大语言模型 API 可以用于聊天或其他生成任务，但它们通常不提供 PaperPiggy 所需的嵌入与重排接口，不能直接替换知识库检索引擎。

## 申请硅基流动 Key

<div class="steps" markdown="1">

### 注册并完成实名认证

打开 [硅基流动登录页](https://account.siliconflow.cn/zh/login)，注册或登录账户，按照网站提示完成实名认证。

### 创建 API Key

进入账户中的“API 密钥”页面，创建一个新的 Key。这个 Key 会填入 PaperPiggy 的首次向导。

### 建议充值 1 元

即使要使用的检索模型是免费的，也建议让账户余额高于零。余额为零时，硅基流动可能拒绝免费模型请求并返回余额不足；充值 1 元后，免费模型仍然不会扣掉这笔余额。

</div>

<div class="callout warn">
  硅基流动的 <code>.cn</code> 与 <code>.com</code> 账户彼此独立。注册、充值和创建 Key 时要使用同一套站点与账户。
</div>

## 完成首次向导

打开 PaperPiggy 后，按以下顺序操作：

1. 在“配 Key · 引擎”中填写 SiliconFlow API Key；
2. 点击“测试连接”，确认嵌入和重排模型都可用；
3. 选择“API 模式”；
4. Base URL 保持应用默认值；
5. 嵌入模型保持 <code>BAAI/bge-m3</code>；
6. 重排模型保持 <code>BAAI/bge-reranker-v2-m3</code>；
7. 再次确认连接成功，然后进入“连接文库”。

通常只需要填写 Key，其他字段保持默认。

## 这把 Key 会用在哪里

同一把硅基流动 Key 可以供 PaperPiggy 的多项功能复用：

- API 检索引擎；
- 文件夹模式的题录抽取；
- 应用内对话；
- 服务端生成检索摘要；
- 其他使用免费模型的小功能。

Agent 本身使用什么模型，由 Claude Code、Codex 或其他 Agent 客户端决定，和这把检索 Key 不是同一层设置。

## API 模式意味着什么

API 模式在检索和建库时会把必要的文本发送给硅基流动完成嵌入或重排。原始 Zotero 文库仍在本机，PaperPiggy 不会修改它。

如果你的使用场景要求检索过程完全离线，可以改用本地模式；本地模式的模型下载、内存占用和切换注意事项见[进阶设置]({{ '/advanced/' | relative_url }})。

## 配置完成检查

<ul class="checklist">
  <li>SiliconFlow Key 测试成功。</li>
  <li>检索引擎选择了 API 模式。</li>
  <li>嵌入与重排模型保持应用默认值。</li>
  <li>已经进入“连接文库”步骤。</li>
</ul>

<div class="page-next">
  <a href="{{ '/quick-start/' | relative_url }}">← 10 分钟快速开始</a>
  <a href="{{ '/library/' | relative_url }}">下一章：连接 Zotero 建库 →</a>
</div>
