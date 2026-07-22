---
layout: default
title: 安装与配置 API
kicker: 第 2 章 · 基础设置
description: 安装 PaperPiggy，分清检索引擎、检索摘要和对话模型，再配置 SiliconFlow 云端检索。
last_reviewed: 2026-07-22
---

## 下载与安装

从 [PaperPiggy Releases](https://github.com/DrinkTea905/paper-piggy/releases/latest) 下载最新的 Windows 安装器。当前正式分发的是 Windows 版本；macOS 暂时只能从源码运行。

安装时建议选择：

- 空间充足的磁盘；
- 自己有正常读写权限的位置；
- 不会被系统清理软件自动清理的位置。

PaperPiggy 的应用、索引、模型和 Agent 工作区会集中在同一套数据目录中，日后迁移和备份更清楚。

## 配置检索所需的 API

PaperPiggy 的检索不只是把问题发给一个聊天模型。它还需要：

- **嵌入模型**：把问题和文献转换成可比较的语义向量；
- **重排模型**：把候选结果重新排序，提高相关性；
- **大语言模型**：用于检索摘要、题录抽取或应用内对话；它和检索引擎不是同一项配置。

硅基流动同时提供 PaperPiggy 已配置好的嵌入和重排模型，而且这两个模型当前可以免费调用。首次配置时，选择“SiliconFlow 云端检索”即可。

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

<figure class="doc-image">
  <img src="{{ '/assets/siliconflow-api-key.png' | relative_url }}" alt="硅基流动后台的 API 密钥与余额充值入口">
  <figcaption>登录硅基流动后，在左侧找到“API 密钥”和“余额充值”。</figcaption>
</figure>

<div class="callout warn">
  硅基流动的 <code>.cn</code> 与 <code>.com</code> 账户彼此独立。注册、充值和创建 Key 时要使用同一套站点与账户。
</div>

## 完成首次向导

打开 PaperPiggy 后，按以下顺序操作：

1. 在“选择检索方式”中选择“SiliconFlow 云端检索”；
2. 填写 SiliconFlow API Key；
3. 点击“测试嵌入与重排”；
4. 连接成功后进入“连接文库”。

普通用户只需要填写 Key。Base URL、嵌入模型和重排模型已固定为适配值，不会在首启向导中干扰选择。

## 这把 Key 会用在哪里

同一把硅基流动 Key 可以供 PaperPiggy 的多项功能复用：

- SiliconFlow 云端检索；
- 文件夹模式的题录抽取；
- 应用内对话；
- PaperPiggy 自动生成检索摘要（选择“复用检索引擎的 SiliconFlow Key”时）；
- 其他使用免费模型的小功能。

Agent 本身使用什么模型，由 Claude Code、Codex 或其他 Agent 客户端决定，和这把检索 Key 不是同一层设置。

## 检索摘要可以另选 AI 厂商

深索把全文拆成可检索小段，负责精读和原文定位；检索摘要是在深索之后为整篇文献增加的一段 AI 摘要，帮助系统更容易先找到它。检索摘要不是题录里的原文摘要，也不能替代深索；没有检索摘要，已深索全文仍可读取和引用。

在“设置 → 建库 → 检索摘要”选择“PaperPiggy 自动生成”后，可以直接二选一：

| 来源 | 模型与费用 | 影响范围 |
|---|---|---|
| 复用检索引擎的 SiliconFlow Key | 固定使用当前免费的简单模型，生成较快 | 只生成检索摘要 |
| 使用其他 AI 厂商 | 可选 DeepSeek、Kimi、智谱、OpenAI 或兼容服务，自选模型；通常按量收费 | 只生成检索摘要，不改变检索引擎 |

两项会直接显示在“PaperPiggy 自动生成”下面。选择其他厂商并点击“保存并测试”时，会真实调用一次所选模型，可能产生少量费用。

## SiliconFlow 云端检索意味着什么

云端检索在检索和建库时会把必要的文本发送给 SiliconFlow 完成嵌入或重排。原始 Zotero 文库仍在本机，PaperPiggy 不会修改它。

如果你的使用场景要求待检索文本不离开电脑，可以改用本地模式；本地模式的模型下载、内存占用和切换注意事项见[进阶设置]({{ '/advanced/' | relative_url }})。

## 配置完成检查

<ul class="checklist">
  <li>SiliconFlow Key 测试成功。</li>
  <li>检索引擎选择了 SiliconFlow 云端检索。</li>
  <li>嵌入与重排测试均通过。</li>
  <li>已经进入“连接文库”步骤。</li>
</ul>

<div class="page-next">
  <a href="{{ '/quick-start/' | relative_url }}">← 10 分钟快速开始</a>
  <a href="{{ '/library/' | relative_url }}">下一章：连接 Zotero 建库 →</a>
</div>
