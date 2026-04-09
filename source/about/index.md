---
title: 关于我
date: 2026-04-08
layout: about
---

<div style="text-align: center; padding: 20px 0 30px;">
  <p style="margin-top: 12px; font-style: italic; color: #888;">"种下一棵树最好的时间是十年前，其次是现在"</p>
</div>

---

## 🙋 个人简介

你好！我是 **丁一帆**

这个博客用来记录我的[学习笔记 / 技术探索 / 项目经验]，希望对你有所帮助。

---

## ✨ 研究兴趣

我当前的主要研究大语言模型（LLM），关注 **数据合成**，**强化学习**，**Agent**以及**Agentic RL**等方向。

我也关注大模型的**下游应用**，例如**deep research**和**vibe coding**。

---

## 🎓 教育背景

**上海财经大学** · 软件工程 · 硕士
*[2024] – [2027]*

**上海财经大学** · 计算机科学与技术 · 本科
*[2020] – [2024]*
[GPA: 3.57/4.00 Rank: 4/52]

---

## ⭐ 学术研究

### 强化学习
**DPO-Δ: Direct Preference Optimization with Residual Layer Duplication**
**研究背景：**现有的dpo训练方法通常无法提供准确的奖励信号，并且需要对所有原始参数进行训练，训练成本较高。
**更加精准的奖励信号：**通过冻结主干网络参数并复制关键层，仅训练复制层参数实现高效偏好优化，设计残差学习机制，利用原始层与复制层输出logits的差值作为残差叠加，在保持原模型能力的同时实现精准对齐，在小模型指导大模型生成的场景下尤其有效。
**显存消耗降低：**由于只需要训练部分参数，方法显著降低训练显存与计算开销，为大规模语言模型的轻量化对齐提供新范式。
**性能突破：**在AlpacaEval上相比原始dpo性能提升9.67%，证明了我们的方法有效提供了更加精准的奖励信号，并且需要的可训练参数仅有原始模
型的3/4。

### 数据合成
**Fanno: Augmenting High-Quality Instruction Data with Open-Sourced LLMs Only**
**ACL2025**
**论文地址：**https://aclanthology.org/2025.findings-acl.906/
**研究背景：**指令微调是提升大语言模型任务执行能力的关键手段，但高质量的指令数据通常依赖人工标注或昂贵的闭源模型，成本高、可扩展性差，现有开源方案仍需种子数据或存在数据多样性不足的问题。
**UCB动态上下文选择方法：**引入UCB算法动态选择高质量指令作为上下文示例，增强生成指令的复杂性与多样性，并设计反例prompt，将示例作为反例，促使模型生成更具创新性的指令。
**性能突破：**基于FANNO生成的10k条数据进行微调，在AlpacaEval和Arena-Hard测试集上正确率分别达到30.13%和31.62%，性能显著超越依赖GPT-4的现有方法。

**Document-Based or Document-Inspired: A Novel Approach for High-Quality Instruction Data Synthesis**
**研究背景：**现有数据合成方法多依赖 GPT-4 等闭源模型，成本高昂，且合成数据存在多样性不足、质量参差不齐等问题。
**高质量指令数据完整合成pipeline：**方法包含以下两个关键步骤：文档属性提取与问题生成、指令质量增强（含复杂度评分与多样性过滤），提升模型泛化能力，在AlpacaEval，Arena-Hard等多个测试集上达到SOTA。
**特定领域数据合成：**进一步在数学领域进行领域特定数据合成实验，在 GSM8K、MATH、DM-MATH 等基准上显著超越多个数学指令数据集，验证了方法的泛化性与灵活性。
**性能突破：**与baseline相比，仅使用10k数据规模就在AlpacaEval、Arena-Hard和TruthfulQA等多个测试集上达到SOTA，在Arena-Hard测试集上正确率可达44.34%，在数学领域上，在GSM8K、MATH等多个任务集上平均正确率可达31.64%，显著超过baseline。

### 大模型数据隐私安全
**Layer-Adaptive Membership Inference: Dynamic Perplexity Calibration for Training Data Detection**
**研究背景：**面向大模型数据隐私安全的成员推理攻击（Membership Inference Attack, MIA）是模型安全领域的核心研究方向之一，MIA通过分析模型输出的统计特征，精准推断特定数据样本是否被用于模型训练，对评估训练数据隐私泄露风险具有重要意义。
**层重要性自适应选择：**提出了一种层重要性自适应选择机制，通过引入轻量级可训练参数层，量化神经网络各层对成员身份推断的敏感程度。基于层权重动态调整前后的数据困惑度（Perplexity）差异，构建高区分度的成员身份判别指标，实现对训练数据的有效识别。
**性能突破：**在WikiMIA和MIMIR数据集上进行验证，相比现有最优基线方法，攻击准确率平均提升8.9%，显著增强了成员推理攻击的有效性和鲁棒性。

## 💼 实习经历

**vivo上海研发中心** · 影像算法研究员
*2025.7 – 2025.11*
**主导美学评估大模型搭建**
**采用技术：**sft，数据合成与增强，强化学习，grpo，dpo
**工作概述：**使用Qwen2.5-7B-Instruct作为底座模型，采用sft、dpo和grpo等不同的训练策略，在AVA，PARA，TAD66K等多个美学数据集上的回归分数预测效果提升5%以上，通过vllm进行线上部署使用。
**方法：**首先使用cot数据，引入grpo和dpo对模型进行强化学习训练，使模型拥有对美学特征做出详细分析和评价的能力，由于大语言模型对数值型分数差异不敏感，使用额外一个模型创新性的引入token as score方法，使用多个固定的token来表征数值型分数，提高了模型的数值预测能力。

## 🛠 技能

### 编程语言
**python**， **C++**

### 框架 & 工具
**llamafactory**，**trl**，**verl**
**claude code**，**openclaw**

---

## 📬 联系我

- GitHub：[github.com/kissshhot](https://github.com/kissshhot)
- Email：2024214406@stu.sufe.edu.cn
