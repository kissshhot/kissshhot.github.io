---
title: Claude Code 国内使用指南
date: 2026-02-08
tags:
  - AI工具
  - Claude Code
  - 开发工具
categories:
  - 技术笔记
---

本文整理自腾讯云开发者社区，介绍如何在国内顺畅使用 Claude Code 进行 AI 编程。

<!-- more -->

## 核心思路

国内使用 Claude Code 主要有两条路：

- **国产模型替代**：用 Qwen Code v0.5.0 或 GLM-4.7，延迟低、成本低，适合日常代码补全与重构
- **原版中转**：通过灵芽 API 等中转服务调用 Claude Opus 4.5，适合复杂架构设计与深层逻辑推理

## 安装

需要 Node.js v24+，使用国内镜像源安装：

```bash
npm install -g @anthropic-ai/claude-code --registry=https://registry.npmmirror.com
```

## 配置环境变量

**macOS / Linux：**

```bash
export ANTHROPIC_API_KEY="sk-your-key"
export ANTHROPIC_BASE_URL="your-provider-url"
```

**Windows PowerShell：**

```powershell
$env:ANTHROPIC_API_KEY="sk-your-key"
$env:ANTHROPIC_BASE_URL="your-provider-url"
```

> Windows 修改环境变量后需重启终端或 VS Code 才能生效。

## 模型性能对比

| 维度 | Qwen Code v0.5.0 | GLM-4.7 | Claude Opus 4.5 |
|------|:-:|:-:|:-:|
| 响应延迟 | ≈150ms | ≈400ms | ≈1.5~2.5s |
| 上下文窗口 | 128k | 1M | 2M |
| 使用成本 | 极低 | 中等 | 高 |

## 常见问题

**模型名称映射**：Qwen Code v0.5.0 可能需要用 `qwen-code-latest` 或 `qwen-2.5-coder-turbo` 作为模型名。

**工具调用格式错误**：GLM-4.7 与 Anthropic 协议存在差异，可在系统提示中约束输出格式。

**成本优化策略**：先用国产模型测试指令，确认后切换到 Opus 4.5 执行，"混合专家"策略可大幅降低成本。

## 总结

国产模型已经足够应对大多数日常编程任务，追求极致效果时再切换到 Claude Opus 4.5。两者结合是目前国内使用 Claude Code 的最优解。
