---
title: 12-Factor Agents：构建可靠 LLM Agent 的十二条原则
date: 2026-04-14
tags:
  - AI Agent
  - LLM
  - 工程实践
  - 软件架构
  - Prompt Engineering
categories:
  - 技术笔记
---

[12-Factor Agents](https://github.com/humanlayer/12-factor-agents) 是 HumanLayer 的 Dex Horthy 发起的一个开源项目，灵感来自经典的 [12-Factor App](https://12factor.net/) 方法论，专注于为构建生产级 LLM Agent 提供可落地的工程原则。

这套框架的核心观点很朴素：**大多数成功的 AI 产品并不是"纯 Agentic"的**。它们是确定性代码与策略性 LLM 决策点的结合体，而不是把一切都交给 Agent 框架自动运转。

<!-- more -->

## 背景：为什么需要这套原则？

当前 AI 应用开发有一个常见的误区：把所有工作都交给 Agent 框架，期望它自动完成复杂任务。然而现实是，那些在生产环境中表现优秀的 AI 功能，往往是由工程师自己掌控 Prompt、上下文和控制流，而不是完全依赖黑盒框架。

Dex 的观察是：**最快把高质量 AI 软件交到用户手中的路径，是把 Agent 构建中的小型、模块化概念引入现有产品，而不是推倒重建**。

---

## 十二条原则详解

### Factor 1：自然语言转工具调用（Natural Language to Tool Calls）

Agent 最核心的能力之一：将用户的自然语言意图转化为结构化的函数调用。

例如，用户说"给 Terri 创建一个 750 美元的付款链接，用于赞助二月 AI 聚会"，Agent 需要将其解析为：

```json
{
  "function": "create_payment_link",
  "parameters": {
    "amount": 750,
    "recipient": "Terri",
    "description": "February AI Tinkerers Meetup Sponsorship"
  }
}
```

LLM 负责理解意图并输出结构化对象，确定性代码负责执行。这是人机协作的基础分工。

---

### Factor 2：掌控你的 Prompt（Own Your Prompts）

> 你的 Prompt 是应用逻辑与 LLM 之间的核心接口。

不要把 Prompt 藏在框架的抽象层后面。框架提供的默认 Prompt 是个好的起点，但对于生产系统来说，它往往缺乏可调节性。

**正确做法：**
- 把 Prompt 当作一等公民的代码来管理
- 对 Prompt 进行版本控制、测试和迭代
- 清楚地知道 LLM 实际收到了什么

好的 Prompt 工程意味着你能精确控制 Agent 的行为，而不是猜测框架在背后做了什么。

---

### Factor 3：掌控你的上下文窗口（Own Your Context Window）

LLM 本质上是无状态的——它每次都需要从上下文中重建世界观。上下文工程（Context Engineering）因此成为一项关键技能。

上下文包括：
- 系统 Prompt 和指令
- 通过 RAG 检索的外部数据
- 历史工具调用及其结果
- 相关对话记忆
- 结构化输出规范

**自定义上下文的优势：**
1. **信息密度**：让数据排布更符合 LLM 的理解模式
2. **错误处理**：以便于恢复的格式呈现失败信息
3. **安全过滤**：在 LLM 接触前过滤敏感数据
4. **灵活实验**：自由尝试各种上下文结构
5. **Token 效率**：在保持清晰的前提下减少 Token 消耗

```python
class Event:
    type: str
    data: dict

class Thread:
    events: list[Event]
    
    def to_prompt(self) -> str:
        # 将事件序列序列化为 LLM 友好的格式
        ...
```

---

### Factor 4：工具即结构化输出（Tools Are Structured Outputs）

工具调用的本质是：**让 LLM 输出一段结构化的 JSON，再由确定性代码执行它**。

这个视角很重要。它意味着工具调用和普通的结构化输出没有本质区别，都可以用 schema 验证，都可以测试，都可以版本化。把工具调用看作"特殊魔法"只会增加不必要的复杂度。

---

### Factor 5：统一执行状态与业务状态（Unify Execution State and Business State）

Agent 的状态和应用的业务状态必须保持同步。

一个常见的陷阱是：Agent 内部维护一套状态，数据库里维护另一套，两者逐渐产生漂移，导致难以调试的一致性问题。

正确做法是把 Agent 的执行状态直接映射到业务实体上，让两者共享同一个真实来源（single source of truth）。

---

### Factor 6：支持启动/暂停/恢复（Launch/Pause/Resume with Simple APIs）

生产级 Agent 必须支持可控的生命周期管理。

- **启动**：通过简单 API 触发 Agent 任务
- **暂停**：在等待人工审批或外部事件时挂起
- **恢复**：从断点继续，而非重头开始

这需要 Agent 能够持久化其状态，并在恢复时正确重建上下文。设计简洁的控制接口是关键。

---

### Factor 7：用工具调用联系人类（Contact Humans with Tool Calls）

人在环（Human-in-the-Loop）不应该是事后加上去的补丁，而应该是 Agent 设计的一等公民。

当 Agent 遇到：
- 高风险操作（如删除数据、发送邮件）
- 超出权限范围的决策
- 需要人工判断的模糊情况

它应该通过**工具调用**的方式请求人工介入，而不是自行猜测或直接执行。这让人类审批自然地融入 Agent 的工作流中。

---

### Factor 8：掌控你的控制流（Own Your Control Flow）

不要把控制流完全交给框架的"自动循环"。

不同类型的工具调用应该有不同的处理逻辑：

| 情景 | 处理方式 |
|------|----------|
| 请求澄清 | 暂停执行，等待人工输入 |
| 获取 Git 标签 | 同步执行，立即继续循环 |
| 部署后端服务 | 暂停，等待人工审批后再执行 |

关键能力：**在工具被选择和被执行之间的那个时刻介入**。没有这种粒度控制，你要么接受高风险操作全部自动执行，要么把 Agent 限制在只能做低风险任务。

---

### Factor 9：将错误压缩进上下文窗口（Compact Errors into Context Window）

错误处理不是"打印报错然后崩溃"，而是把失败信息高效地整合回上下文，让 Agent 有机会自我修正。

原则是：
- 错误信息要**简洁**，不要把完整的 stack trace 塞进上下文
- 错误要**可操作**，帮助 LLM 理解如何纠正
- 避免错误信息占用过多宝贵的上下文窗口

---

### Factor 10：小而专注的 Agent（Small, Focused Agents）

**专才胜过通才**。

一个处理支付的 Agent、一个处理用户认证的 Agent、一个处理邮件的 Agent——比一个什么都能做的万能 Agent 更可靠、更易维护。

小型 Agent 的优势：
- 更容易测试和调试
- Prompt 更简洁，减少 LLM 混淆
- 更容易替换或升级单个组件
- 故障范围更小，影响更可控

---

### Factor 11：从任何地方触发（Trigger from Anywhere）

优秀的 Agent 应该与用户相遇在用户所在的地方，而不是强迫用户适应 Agent 的接口。

这意味着 Agent 应该可以被：
- Slack 消息触发
- Webhook 调用触发
- 定时任务触发
- API 请求触发
- 邮件触发

多渠道触发能力让 Agent 真正融入用户的工作流，而不是成为孤立的工具。

---

### Factor 12：无状态 Reducer 模式（Stateless Reducer Pattern）

借鉴函数式编程的 fold/reduce 思想，把 Agent 设计为**纯函数**：

```
(当前状态 + 新事件) → 新状态
```

Agent 不维护内部状态，每次执行都是对输入数据的纯粹变换。这带来：
- **可预测性**：相同输入必然产生相同输出
- **可测试性**：无副作用，单元测试简单
- **可组合性**：多个 Agent 可以像函数一样组合

这是整个框架的架构基础，也是让 Agent 系统在分布式环境下保持可靠性的关键。

---

## 核心洞见

12-Factor Agents 给出了一个清醒的视角：

1. **Agent 框架不是银弹**。框架能帮你快速起步，但生产级的可控性需要你自己动手。

2. **确定性代码 + 策略性 LLM = 可靠 AI**。不要把所有决策都丢给 LLM，让 LLM 做它擅长的（理解意图、生成结构化输出），让确定性代码做它擅长的（执行、验证、状态管理）。

3. **控制力是可靠性的前提**。掌控 Prompt、上下文、控制流，才能真正掌控 Agent 的行为，才能在出问题时快速定位和修复。

---

## 小结

这套框架的价值不在于它有多"新颖"，而在于它把工程师在生产实践中踩过的坑系统化成了可复用的原则。如果你正在构建 LLM 应用，这十二条原则值得逐一对照自己的系统检查一遍。

项目地址：[github.com/humanlayer/12-factor-agents](https://github.com/humanlayer/12-factor-agents)
