---
layout: default
title: 10 分钟快速开始
kicker: 第 1 章 · 基础设置
description: 用最短路径完成 SiliconFlow 云端检索、Zotero 建库和 Agent 接入。十分钟内不追求整库深索完毕。
last_reviewed: 2026-07-22
---

<div class="callout tip">
  <strong>本章的完成标准：</strong>PaperPiggy 已经读到你的 Zotero 文库，第一版索引已经建立，Agent 能够查看知识库状态并搜索文献。全文深索可以之后慢慢完成。
</div>

## 开始前准备

- Windows 10/11 电脑；
- 已经安装并使用 Zotero；
- Zotero 中至少有几篇带全文附件的文献；
- 一个可以完成实名认证的硅基流动账户；
- 一个支持 MCP 的 AI 助手，例如 Claude Code 或 Codex。

## 第一步：安装 PaperPiggy

前往 [PaperPiggy 最新版本](https://github.com/DrinkTea905/paper-piggy/releases/latest)，下载 Windows 安装器并完成安装。建议选择空间充足、自己有正常读写权限的位置。

安装完成后打开 PaperPiggy，首次使用向导会自动出现。

## 第二步：选择检索方式

首次向导的“选择检索方式”提供两项：

- **本地模式**：检索文本不发给外部服务，首次要下载约 1.2 GB 模型；
- **SiliconFlow 云端检索**：免下载、适合快速开始，检索时会联网并发送待检索文本。

推荐新用户先选 SiliconFlow 云端检索。知识库检索同时需要“嵌入”和“重排”两项专用能力，普通 DeepSeek、Kimi、OpenAI 对话 API 不能直接用于知识库检索。SiliconFlow 云端检索当前免费。

## 第三步：申请并填写 SiliconFlow API Key

打开 [硅基流动官网](https://account.siliconflow.cn/zh/login)，登录并完成实名认证，然后进入“API 密钥”页面创建一个 Key。

虽然 PaperPiggy 使用的嵌入和重排模型可以免费调用，仍建议账户充值 **1 元**。硅基流动账户余额为零时，免费模型也可能返回余额不足错误；充值后，免费模型本身不会扣掉这 1 元。

回到首次向导：

1. 把刚申请的 SiliconFlow API Key 粘贴进去；
2. 点击“测试嵌入与重排”；
3. 连接成功后进入“连接文库”。

粘贴 Key 并完成测试后，即可连接文库。本地模式见[进阶设置]({{ '/advanced/' | relative_url }})。

## 第四步：连接 Zotero

向导通常会自动找到 Zotero。选择“连接 Zotero”，然后点击“连接文库”。

如果没有自动找到，在 Zotero 的“首选项 → 高级 → 文件和文件夹”中查看数据目录，把包含 <code>zotero.sqlite</code> 的目录填入 PaperPiggy。

连接只读取 Zotero 的题录、附件和分类，不会修改 Zotero 数据。

## 第五步：建立第一版索引

点击“开始建立索引”。题录索引会很快完成，语义索引随后在后台提升检索质量。

进入主界面后如果看到“深索全库”的邀请，第一次不要急着全部启动。大型文库的全文处理会持续很久；先完成 Agent 连接，再让 Agent 根据你的研究方向安排优先顺序。

## 第六步：连接 Agent

打开 PaperPiggy 顶栏的“Agent”页：

1. 选择你使用的客户端；
2. 复制页面生成的接入命令；
3. 在任意 Claude Code 或 Codex 会话中粘贴运行；
4. 重新进入或刷新会话。

不要从本教程手抄端口、路径或配置。应用内的命令已经填好了你电脑上的真实安装位置。

## 第七步：做第一次验证

连接完成后，直接对 Agent 说：

<div class="prompt">检查我的 PaperPiggy 知识库状态，告诉我已经入库多少篇、多少篇完成深索、多少篇缺少检索摘要；然后搜索一个库里确实存在的主题，列出最相关的 5 篇文献。</div>

如果它能返回知识库状态和真实文献，基础设置就完成了。

## 接下来做什么

不要马上把一切都深索完。更稳妥的顺序是：

1. 先让 Agent 深索你当前课题最相关的一批文献；
2. 按需为这些文献生成检索摘要；没有摘要也不影响读取已深索全文；
3. 开始实际研究；
4. 电脑夜间空闲时，再逐步处理剩余文库。

<div class="prompt">先审查我的知识库建设状态。围绕“我的当前课题”，挑选最值得优先处理的文献，分批完成深索和检索摘要。不要立刻启动整库任务；先给我处理顺序和预计工作量。</div>

<div class="page-next">
  <a href="{{ '/' | relative_url }}">← 教程首页</a>
  <a href="{{ '/install/' | relative_url }}">下一章：安装与配置 API →</a>
</div>
