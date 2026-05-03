---
title: "今日 AI 热点速览 0503"
description: "五角大楼 AI 合约风波、Anthropic Mythos 「危险级」模型、Google $400 亿投资 Anthropic、AlphaEvolve 算法突破，以及 Vibe Coding 年度横评。"
slug: "ai-news-0503"
date: 2026-05-03T10:00:00+08:00
lastmod: 2026-05-03T10:00:00+08:00
draft: false
categories:
  - AI 热点
tags:
  - Anthropic
  - Claude
  - 五角大楼
  - Vibe Coding
  - DeepMind
  - 每日速览
---

> 每日 AI 热点采集，聚焦 Vibe Coding、Claude 生态、AI Agent、模型更新、新产品和行业大事。

---

## 🏢 模型厂商动态

### 1. Anthropic Mythos — 史上最强安全模型，仅向精选合作伙伴开放

Mythos Preview 于 4 月 7 日发布，但 **不公开**。原因：该模型可自动发现"数万个"安全漏洞，Anthropic 认为其威力过强，不宜对外开放。

通过 **Project Glasswing**，Anthropic 仅向 40+ 家关键基础设施和网络安全组织开放，并承诺：
- 提供 **$1 亿** 使用积分
- 向开源安全组织直接捐赠 **$400 万**

- 官方预览：[red.anthropic.com](https://red.anthropic.com/2026/mythos-preview/)
- 报道：[Axios — Anthropic withholds Mythos Preview](https://www.axios.com/2026/04/07/anthropic-mythos-preview-cybersecurity-risks)

---

### 2. Google Deep Research Max 发布

基于 **Gemini 3.1 Pro** 构建，面向长周期自主研究：

- 新增 **MCP 支持**，可接入自定义数据源
- 原生可视化输出
- 支持跨 Web 和私有知识库的深度调研

- 来源：[Google Blog](https://blog.google/innovation-and-ai/models-and-research/gemini-models/next-generation-gemini-deep-research/)

---

## 🔥 今日头条：五角大楼 AI 合约大戏

### 3. 五角大楼向 7 家公司授予机密 AI 合约，Anthropic 被踢出局

**5 月 1 日**，五角大楼宣布向以下公司颁发机密网络 AI 合约：

> OpenAI、Google、微软、AWS、Nvidia、SpaceX、Reflection AI

**Anthropic 被排除**，原因是拒绝允许五角大楼将 Claude 用于"所有合法目的"——Anthropic 认为这一措辞可能涵盖国内大规模监控或全自主武器。

事件背景：
- 国防部长 Pete Hegseth 于 3 月正式将 Anthropic 列入供应链风险名单
- Anthropic 随后对特朗普政府提起诉讼
- 加州联邦法官上月已阻止政府的相关行动

- [CNN Business](https://www.cnn.com/2026/05/01/tech/pentagon-ai-anthropic) | [DefenseScoop](https://defensescoop.com/2026/05/01/dod-expands-classified-ai-work-with-8-companies-excluding-anthropic/) | [The Next Web](https://thenextweb.com/news/pentagon-ai-deals-anthropic-safety-limits)

---

## 💰 融资 / 合作

### 4. Google 宣布向 Anthropic 投资最高 400 亿美元

- 估值：**3500 亿美元**
- Google 先投 **$100 亿**，达成特定目标后再追加 $300 亿
- Anthropic 2026 年年化收入已突破 **$300 亿**（2025 年底约 $90 亿）

值得注意：[Fortune 报道](https://fortune.com/2026/04/30/google-amazon-ai-profits-anthropic-stake-bubble-earnings-2026/)指出，Google 和 Amazon 的"AI 盈利"有一半来自 Anthropic 股权升值，而非实际业务，并警示泡沫风险。

- 来源：[TechCrunch](https://techcrunch.com/2026/04/24/google-to-invest-up-to-40b-in-anthropic-in-cash-and-compute/)

---

## 🔬 AI 研究

### 5. DeepMind AlphaEvolve — 用 Gemini + 进化算法自动发现新算法

AlphaEvolve 将 Gemini 与进化算法结合，流程是：

1. Gemini 提出新算法候选
2. 进化算法评估并筛选最优
3. 最优结果反馈给 Gemini 继续迭代

Google DeepMind 已将其用于**优化数据中心电力消耗**和 **TPU 芯片设计**。

- 来源：[Google DeepMind Blog](https://deepmind.google/blog/)

---

## 🧑‍💻 Vibe Coding / 开发者实践

### 6. Claude Code vs Cursor vs Codex — 2026 年度横评

| 工具 | 优势 | SWE-bench |
|------|------|-----------|
| Claude Code | 复杂规划、大型任务、多文件操作 | **72.5%** |
| Cursor | IDE 内实时编码、自动补全 | 55–62% |
| Codex 3.0 | 端到端编码、自动 PR、CI 集成 | — |

**主流建议**：Cursor 负责日常 IDE 内速度，Claude Code 负责架构级复杂任务，两者结合效率最高。调查显示 **70% 开发者**在编码任务上偏好 Claude。

- [Northflank 深度对比](https://northflank.com/blog/claude-code-vs-cursor-comparison) | [Viblo 横评](https://viblo.asia/p/cursor-vs-claude-code-vs-codex-which-is-better-for-vibe-coding-in-2026-bA468ealLKv)

---

## 🚀 新产品 / Product Hunt

### 7. 本周值得关注的 AI 工具

| 产品 | 一句话描述 |
|------|-----------|
| **Codex 3.0** (OpenAI) | 端到端编码 + 自动 PR + CI 自动化 |
| **Montage** | 将模型意图转为确定性服务端渲染界面 |
| **Lovable** | 快速 MVP 创建，可视化编辑 + GitHub 同步 |
| **Quanto** | 自动化会计销售和 onboarding 的垂直 AI Agent |

- 来源：[Product Hunt AI Agents](https://www.producthunt.com/categories/ai-agents)

---

## 💬 社区热议

### 8. r/ClaudeAI：Claude Pro 值不值得订阅？

社区分歧点：
- 每天靠 Claude 写代码的开发者：**值得**，高峰期用量限制是核心痛点
- 轻度用户：免费版够用

**最大抱怨**：高峰期平台稳定性差，短暂宕机即打断整个工作流。

- 来源：[AI Tool Discovery 社区汇总](https://www.aitooldiscovery.com/guides/claude-reddit)

---

**今日关键词**：`#Mythos` `#五角大楼AI合约` `#VibeCoding` `#AlphaEvolve` `#Google投资Anthropic`
