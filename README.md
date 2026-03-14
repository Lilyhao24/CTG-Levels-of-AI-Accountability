# CTG Model: AI 状态连续性、可追溯性与治理问责模型

**AI State-Continuity, Traceability & Governance Framework**

[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-sa/4.0/)
[![Version](https://img.shields.io/badge/version-3.2-blue.svg)]()
[![Status](https://img.shields.io/badge/status-draft--RFC-orange.svg)]()

> [English Version below](#english-version)

---

## 这是什么？

CTG 是一个开源的 AI 责任分级框架，沿三个轴对 AI 系统进行分类：

- **C 轴（状态连续性）**：AI "记得"多少？（C0 → C3b）
- **T 轴（可追溯基础设施）**：AI 被"看到和质询"多少？（T0 → T3）
- **G 轴（治理问责）**：出了事，责任能否被清晰地追溯和执行？（G0 → G3）

三轴之间是**有向依赖**关系：C → T → G。

**核心设计原则：**
- AI **不是法律主体**。G 轴的问责主体始终是机构和人。
- T2 要求的是**决策理由接口 (decision justification interface)**，而非可解释模型。
- 每个 CTG 标签必须伴随通俗语言的**局限性声明**（反标签幻觉机制）。
- G3 提供**双轨模式**：G3a（监管指定）/ G3b（认证池自选），适配不同政治环境。

## 为什么需要 CTG？

| 问题 | CTG 的回答 |
|------|-----------|
| "可解释性"对神经网络是伪命题 | 用**可质询性**替代——外部方能否有效挑战输出？ |
| 记忆 ≠ 责任 | 拆为三轴有向依赖，而非正交 |
| AI 标签制造虚假安全感 | 强制**反标签幻觉**披露 |
| 审计购物（企业挑最宽松的审计方） | **强制轮换** + **分层审计** |
| 全球治理环境不同 | G3a（EU 风格）vs G3b（US 风格） |

## 快速参考

```
产品示例                  C      T      G     
──────────────────────────────────────────────
早期 GPT API             C0     T0     G0    
ChatGPT / Claude.ai      C1     T1     G1    
Claude Memory            C2     T1     G1    
金融监管合规 AI           C1     T2     G2    
Netflix 推荐             C3a    T1     G1    
理想化医疗 AI            C2     T3     G3a   
```

## 二维投影可视化

C × T 能力平面 + G 治理覆盖层：

```
        T3 ┤ ·───────────── 全链路可审计
           │
        T2 ┤ ·───────────── 可质询  
           │        ╔══════════════╗
        T1 ┤ ·──────║  当前主流     ║── 日志记录
           │        ║  AI 产品     ║
        T0 ┤ ·──────╚══════════════╝── 无记录
           └──┬──────┬──────┬──────┬──────┬──
             C0     C1     C2    C3a    C3b
           瞬时态  会话态  持久态  在线学习 自主目标
                                         (理论层)

G0─G3 作为治理管辖层叠加在能力平面之上
```

## 文档

| 文档 | 说明 |
|------|------|
| [whitepaper/CTG_Model_v3.2.docx](whitepaper/CTG_Model_v3.2.docx) | 完整白皮书（中文，v3.2 草案） |
| [whitepaper/CTG_Model_v3.2_en.md](whitepaper/CTG_Model_v3.2_en.md) | 英文完整版（English full version） |
| [CHANGELOG.md](CHANGELOG.md) | 版本演进记录 v1.0 → v3.2 |

## 演进历史

本框架经过 **6 轮对抗性审计** 迭代进化：

| 版本 | 关键变更 |
|------|---------|
| v1.0 | 单轴（记忆 = 责任） |
| v2.0 | 双轴（认知 × 问责）+ 可测试判定标准 |
| v2.1 | 正交性边界 + 事后合理化防御 |
| v3.0 | **三轴 (C → T → G)** + 可质询性替代可解释性 |
| v3.1 | 标准质询者 + DDI + 灰匣子存证 + 类别推定 |
| v3.2 | C轴改名"状态连续性" + DDI行为包络线 + G3双轨模式 |

每一次变更都由针对上一版本的具体攻击驱动。

## 如何贡献

### 🔴 最需要的贡献
- **实证标定**：DDI 行为包络线阈值在不同领域如何设定？
- **法律审查**：CTG 如何与各司法管辖区的 AI 法规对接？
- **工具开发**：CTG Evaluator（输入系统描述 → 输出分级）

### 🟢 如何参与
1. **开 Issue 攻击框架** — 最好的贡献就是找到弱点
2. **提交案例分析** — 用 CTG 给真实 AI 产品分级
3. **翻译** — 欢迎改进英文版或翻译其他语言
4. **参与讨论** — Issues 或 Discussions

详见 [CONTRIBUTING.md](CONTRIBUTING.md)

## 第一落地场景

**金融 AI** — 已有成熟的监管基础（MiFID II、巴塞尔协议）、问责文化和审计基础设施。

如果你从事金融 AI 监管或合规工作，你的意见特别有价值。

## 许可证

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

## 引用

```
CTG Model: AI State-Continuity, Traceability & Governance Framework. 
Version 3.2 (Draft). March 2026.
https://github.com/Lilyhao24/CTG-Levels-of-AI-Accountability
```

---

<a name="english-version"></a>

# English Version

## What is CTG?

CTG is an open framework for classifying AI systems along three axes:

- **C (State Continuity):** How much does the AI "remember"? (C0 → C3b)
- **T (Traceability Infrastructure):** How much can the AI be "observed and challenged"? (T0 → T3)
- **G (Governance Accountability):** How clearly can responsibility be traced when things go wrong? (G0 → G3)

The three axes form a **directed dependency**: C → T → G.

**Key design principles:**
- AI is **not a legal subject**. G-axis accountability always rests on institutions and people.
- T2 requires a **decision justification interface**, not an explainable model.
- Every CTG label must include a **plain-language limitation statement** (Anti-Label-Illusion).
- G3 offers **dual-track modes**: G3a (regulator-assigned, EU-style) vs G3b (accredited pool, US-style).

## Why CTG?

| Problem | CTG's Answer |
|---------|-------------|
| "Explainability" is a false promise for neural networks | Replace with **contestability** |
| Memory ≠ Responsibility | Three axes with directed dependency |
| AI labels create false trust | Mandatory **Anti-Label-Illusion** disclosure |
| Audit shopping | **Mandatory rotation** + **layered audit** |
| One-size-fits-all governance | G3a (EU) vs G3b (US) |

## Quick Reference

```
Product Example          C     T     G     
─────────────────────────────────────────
Early GPT API            C0    T0    G0    
ChatGPT / Claude.ai      C1    T1    G1    
Claude Memory            C2    T1    G1    
Financial Compliance AI   C1    T2    G2    
Netflix Recommender      C3a   T1    G1    
Ideal Medical AI         C2    T3    G3a   
```

## 2D Projection

```
        T3 ┤ ·───────────── Full-chain Auditable
           │
        T2 ┤ ·───────────── Contestable  
           │        ╔══════════════╗
        T1 ┤ ·──────║  Most current ║── Logged
           │        ║  AI products  ║
        T0 ┤ ·──────╚══════════════╝── Unrecorded
           └──┬──────┬──────┬──────┬──────┬──
             C0     C1     C2    C3a    C3b
          Transient Session Persistent Online Auto-telic
                                      Learning (Theory)

G0─G3 overlays as regulatory jurisdiction layers
```

## Documents

| Document | Description |
|----------|-------------|
| [whitepaper/CTG_Model_v3.2.docx](whitepaper/CTG_Model_v3.2.docx) | Full whitepaper (Chinese, v3.2 draft) |
| [whitepaper/CTG_Model_v3.2_en.md](whitepaper/CTG_Model_v3.2_en.md) | Full English version |
| [CHANGELOG.md](CHANGELOG.md) | Version history v1.0 → v3.2 |

## Evolution

Evolved through **6 rounds of adversarial review**: v1.0 (single axis) → v2.0 (dual axis) → v2.1 (defense mechanisms) → v3.0 (three axes C→T→G) → v3.1 (Standard Contestor, DDI, Grey-box) → v3.2 (State Continuity rename, Behavior Envelope, G3 dual-track).

## How to Contribute

1. **Open an Issue** to attack the framework
2. **Submit a Case Study** classifying a real AI system
3. **Improve translations** or add new languages
4. **Join Discussions**

See [CONTRIBUTING.md](CONTRIBUTING.md)

## License

[CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/)

---

*"不要定义一个没有边界的框架。要定义一个知道自己边界在哪里的框架。"*

*"Don't define a framework without boundaries. Define a framework that knows where its boundaries are."*
