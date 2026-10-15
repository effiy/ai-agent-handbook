# AI Agent Handbook

[![License](https://img.shields.io/badge/license-Apache%202.0-blue)](./LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/aliyun/ai-agent-handbook?style=social)](https://github.com/aliyun/ai-agent-handbook)
[![Website](https://img.shields.io/badge/阅读站-aliyun.github.io%2Fai--agent--handbook-2ea44f)](https://aliyun.github.io/ai-agent-handbook/)

> **企业级 Agent 构建与落地实践白皮书**<br>从架构设计到生产交付，从治理调优到一线实践，贯穿 Agent 完整生命周期。

[📖 **在线阅读**](https://aliyun.github.io/ai-agent-handbook/) &nbsp;|&nbsp; [📑 **全书目录**](https://aliyun.github.io/ai-agent-handbook/contents.html) &nbsp;|&nbsp; [🧭 **阅读指南**](https://aliyun.github.io/ai-agent-handbook/reading-guide.html) &nbsp;|&nbsp; [💬 **共读交流**](./共读微信群.md)

---

## 目录

- [关于本书](#关于本书)
- [快速开始](#快速开始)
- [全书架构](#全书架构)
- [章节导航](#章节导航)
- [推荐阅读路径](#推荐阅读路径)
- [实践案例速览](#实践案例速览)
- [下一步规划](#下一步规划)
- [参与共建](#参与共建)
- [贡献者](#贡献者)

---

## 关于本书

按照 Agent 的架构、构建、运行、治理和调优应用生命周期，总结了我们在企业级 Agent 落地过程中的实践经验和体会。若白皮书能对个人学习和企业落地 Agent 起到一点点的促进作用，将是我们莫大的荣幸。

谨以此项目，献给参与 AI 建设的所有同行者们。

### 阅读站功能

阅读站提供章节导航、中文全文搜索、图表与图片放大、明暗主题切换和阅读位置记忆。无需登录，搜索索引随站点构建，不依赖外部服务。

> 🖥️ **本地预览**：需 Node.js 22，在仓库根目录执行 `npm ci && npm run dev`。站点维护与发布方法详见 [WEBSITE.md](./WEBSITE.md)。

### 写作背景

2025 年 9 月，我们发布了[《AI 原生应用架构白皮书》](https://developer.aliyun.com/ebook/8479)，围绕 AI 原生应用的 DevOps 全生命周期做了体系化拆解。但随着模型和智能体技术的快速发展，市场关注度已从快速构建智能体，转向以下三大新挑战：

- **工程化挑战**：从概率智能到可靠生产力，Agent 能够承担关键任务。
- **规模化挑战**：稳定、安全、性能、成本——从单点试验到智能基础设施，Agent 能够被大规模部署。
- **组织化挑战**：从 Agent 孤岛到智能组织，Agent 能够进入核心业务流程。

因此，我们重新梳理了白皮书架构，通过更与时俱进的内容、更高的实践篇幅占比、更社区化的协作，为企业选型和内部立项提供参考，并以开源方式长期维护，持续呈现 AI 原生应用架构的前沿思考和落地实践。

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 快速开始

根据你的角色和目标，选择最合适的切入点：

| 你的角色 | 推荐入口 | 核心收获 |
| --- | --- | --- |
| 🧑‍💻 **Agent / AI 应用开发者** | [🔨 构建篇](./02-build/) → [⚙️ 运行篇](./03-run/) → [📈 调优篇](./05-optimization/) | 掌握 Harness、上下文、状态、工具、沙箱、轨迹与评估闭环等核心工程方法。 |
| 🏗️ **架构师与平台工程师** | [🏛️ 架构篇](./01-architecture/) → [⚙️ 运行篇](./03-run/) → [🛡️ 治理篇](./04-governance/) | 建立从组件、平台责任到生命周期的完整架构视图，形成可扩展的 Agent 基础设施设计。 |
| 👔 **技术负责人和研发管理者** | [📊 调研报告](./2026-agent-survey-report.md) → [🏛️ 架构篇](./01-architecture/) → [🏭 实践篇](./06-case-study/) | 判断应用形态、成熟度、投入边界与生产风险，支撑选型、立项和组织协同。 |
| 📊 **产品与业务负责人** | [📊 调研报告](./2026-agent-survey-report.md) → [🏛️ 架构篇](./01-architecture/) → [🏭 实践篇](./06-case-study/) | 理解适合 Agent 的任务、人与 Agent 的责任边界，以及从试点走向核心流程的条件。 |
| 🔒 **安全、质量与运维人员** | [⚙️ 运行篇](./03-run/) → [🛡️ 治理篇](./04-governance/) → [📈 调优篇](./05-optimization/) | 建立可观测、审计、安全授权、上线验证、持续评估和故障归因机制。 |
| 🔬 **研究者与生态贡献者** | [📑 全书目录](https://aliyun.github.io/ai-agent-handbook/contents.html) → [🏭 实践篇](./06-case-study/) | 了解企业一线问题、工程抽象和开放议题，参与完善行业知识体系。 |

> 💡 也可通过阅读站的[阅读指南](https://aliyun.github.io/ai-agent-handbook/reading-guide.html)获取更详细的逐章阅读建议。

完整阅读后，你将能够：

- 从业务目标、任务确定性和风险出发，选择最低充分的 Agent 架构；
- 理解 Model 与 Harness 的责任边界，不把所有问题都归因于模型能力；
- 设计可持续推进、可中断恢复、可验证完成的 Agent 任务系统；
- 为 Agent 建立执行环境、状态、流量、权限、观测与成本治理底座；
- 用 Trace、Trajectory、黄金数据集和评估实验形成持续改进的数据飞轮；
- 将方法映射到研发效能、设计、运维、企业 IT、客户运营等实际场景。

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 全书架构

| 篇章 | 章节 | 🏷️ 导读 | 🌐 阅读站 |
| --- | --- | --- | --- |
| 📊 2026 Agent 开发者调研报告 | — | [源文件](./2026-agent-survey-report.md) | [survey.html →](https://aliyun.github.io/ai-agent-handbook/survey.html) |
| 📖 前言 | — | [源文件](./00-preface/00-preface.md) | [preface.html →](https://aliyun.github.io/ai-agent-handbook/preface.html) |
| 🏛️ 架构篇 | 第 1–2 章 | [导读](./01-architecture/README.md) | [/architecture/ →](https://aliyun.github.io/ai-agent-handbook/architecture/) |
| 🔨 构建篇 | 第 3–6 章 | [导读](./02-build/README.md) | [/build/ →](https://aliyun.github.io/ai-agent-handbook/build/) |
| ⚙️ 运行篇 | 第 7–12 章 | [导读](./03-run/README.md) | [/run/ →](https://aliyun.github.io/ai-agent-handbook/run/) |
| 🛡️ 治理篇 | 第 13–16 章 | [导读](./04-governance/治理篇导读.md) | [/governance/ →](https://aliyun.github.io/ai-agent-handbook/governance/) |
| 📈 调优篇 | 第 17–24 章 | [导读](./05-optimization/调优篇导读.md) | [/optimization/ →](https://aliyun.github.io/ai-agent-handbook/optimization/) |
| 🏭 实践篇 | 第 25–29 章 + Jev 专题 | [导读](./06-case-study/README.md) | [/cases/ →](https://aliyun.github.io/ai-agent-handbook/cases/) |
| 🔭 总结与展望 | [第 30 章](<./07-conclusion/第 30 章 从 Agentic Application 到 Agentic OS.md>) | — | [/outlook/ →](https://aliyun.github.io/ai-agent-handbook/outlook/) |

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 章节导航

> 每章提供两条路径：**📝 源文件**（GitHub Markdown，适合代码级阅读与贡献）和 **🌐 阅读站**（VitePress，支持搜索、导航、主题切换）。

**快速跳转：** [架构篇](#架构篇) · [构建篇](#构建篇) · [运行篇](#运行篇) · [治理篇](#治理篇) · [调优篇](#调优篇) · [实践篇](#实践篇) · [总结与展望](#总结与展望)

### 🏛️ 架构篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 1 章 · AI 原生应用的新阶段 | [GitHub](<./01-architecture/第 1 章　AI 原生应用的新阶段.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-01.html) |
| 第 2 章 · Agentic Application 参考架构 | [GitHub](<./01-architecture/第 2 章　Agentic Application 参考架构.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-02.html) |

> 应用形态演进、Agentic Application 的定义与边界、企业成熟度判断；组件视图、平台责任与生命周期视图。

### 🔨 构建篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 3 章 · Harness 的主流构建方式 | [GitHub](<./02-build/第 3 章 范式：Harness 的主流构建方式和责任边界.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/build/chapter-03.html) |
| 第 4 章 · 任务编排与长程推进 | [GitHub](<./02-build/第 4 章 任务：编排、长程推进与协作流转.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/build/chapter-04.html) |
| 第 5 章 · 上下文、状态与能力资产 | [GitHub](<./02-build/第 5 章 信息：上下文、状态与可复用能力资产.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/build/chapter-05.html) |
| 第 6 章 · 受控执行与验证反馈 | [GitHub](<./02-build/第 6 章 行动：受控执行、验证反馈与交付准备.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/build/chapter-06.html) |

> 高代码框架、产品化 Harness、Managed Agents、Agent 云产品；Agent Loop、任务状态机、计划与门禁；Context Builder、Session、Workspace、Memory、Knowledge、Skill；Action Plane、MCP、A2A、权限与 HITL。

### ⚙️ 运行篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 7 章 · Agent 运行时与沙箱 | [GitHub](<./03-run/第 7 章  Agent 运行时与沙箱.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-07.html) |
| 第 8 章 · Agent 状态存储与语义资产 | [GitHub](<./03-run/第 8 章 Agent 状态存储与语义资产.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-08.html) |
| 第 9 章 · AI 网关与统一流量治理 | [GitHub](<./03-run/第 9 章  AI 网关与统一流量治理.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-09.html) |
| 第 10 章 · Agent 异步任务与自动化 | [GitHub](<./03-run/第 10 章  Agent 异步任务与自动化流程.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-10.html) |
| 第 11 章 · Multi-Agent 协作与编排 | [GitHub](<./03-run/第 11章  Multi-Agent 协作与编排.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-11.html) |
| 第 12 章 · Agent 分布式通信 | [GitHub](<./03-run/第 12 章 Agent 分布式通信.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/run/chapter-12.html) |

> 沙箱、Runtime、工作空间与环境生命周期；Event Log、Checkpoint、Artifact、长期记忆与 RAG；LLM/MCP/Agent 三类流量的统一网关；异步任务、Multi-Agent 编排与分布式通信协议。

### 🛡️ 治理篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 13 章 · Agent 的可观测性 | [GitHub](<./04-governance/第 13 章　Agent 的可观测性.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/governance/chapter-13.html) |
| 第 14 章 · Agent 安全 | [GitHub](<./04-governance/第 14 章　Agent 安全.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/governance/chapter-14.html) |
| 第 15 章 · AI 资产的发现与管理 | [GitHub](<./04-governance/第 15 章　AI 资产的发现与管理.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/governance/chapter-15.html) |
| 第 16 章 · Agent 行为生成与质量验证 | [GitHub](<./04-governance/第 16 章　Agent 行为生成与质量验证.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/governance/chapter-16.html) |

> 指标、日志、Trace、成本归因与审计；Prompt Injection 防护、身份鉴权、高危授权与数据出域；Prompt/Skill/MCP/Agent 的注册、版本与依赖管理；用户模拟、环境模拟与上线前 Agent Simulation。

### 📈 调优篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 17 章 · 模型调优 | [GitHub](<./05-optimization/第 17 章　模型调优.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-17.html) |
| 第 18 章 · Agent 调优总览 | [GitHub](<./05-optimization/第 18 章　Agent 调优总览.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-18.html) |
| 第 19 章 · Agent 轨迹数据 | [GitHub](<./05-optimization/第 19 章　Agent 轨迹数据.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-19.html) |
| 第 20 章 · Agent 运行时数据处理 | [GitHub](<./05-optimization/第 20 章　Agent 运行时数据处理.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-20.html) |
| 第 21 章 · Agent 黄金数据集 | [GitHub](<./05-optimization/第 21 章　Agent 黄金数据集.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-21.html) |
| 第 22 章 · Agent 优化：Badcase | [GitHub](<./05-optimization/第 22 章　Agent 优化：Badcase.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-22.html) |
| 第 23 章 · 受控自进化 | [GitHub](<./05-optimization/第 23 章　受控自进化.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-23.html) |
| 第 24 章 · 边缘运行时与全球优化 | [GitHub](<./05-optimization/第 24 章　Agent 边缘运行时与全球优化.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-24.html) |

> SFT、Agentic RL、模型蒸馏与上线验收；数据飞轮全景；Trace → Trajectory → 黄金数据集 → Badcase 归因 → 受控自进化；边缘运行时与全球优化。

### 🏭 实践篇

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 25 章 · 研发效能 | [📂 目录](<./06-case-study/第25章 研发效能/>) | [/cases/chapter-25/ →](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/) |
| 第 26 章 · 设计工程 | [📂 目录](<./06-case-study/第26章 设计工程/>) | [/cases/chapter-26/ →](https://aliyun.github.io/ai-agent-handbook/cases/chapter-26/) |
| 第 27 章 · 运维、安全与企业 IT | [📂 目录](<./06-case-study/第27章 运维、安全与企业IT/>) | [/cases/chapter-27/ →](https://aliyun.github.io/ai-agent-handbook/cases/chapter-27/) |
| 第 28 章 · 客户、销售与运营 | [📂 目录](<./06-case-study/第28章 客户、销售与运营/>) | [/cases/chapter-28/ →](https://aliyun.github.io/ai-agent-handbook/cases/chapter-28/) |
| 第 29 章 · GOAI Agent Infra 赛道 | [GitHub](<./06-case-study/第 29 章 GOAI Agent Infra 赛道：多 Agent 协同的前沿实践探索.md>) | [/cases/chapter-29.html →](https://aliyun.github.io/ai-agent-handbook/cases/chapter-29.html) |
| Jev 专题 · 结构化决策实践 | [📂 目录](<./06-case-study/Jev 专题/>) | [/cases/jev/ →](https://aliyun.github.io/ai-agent-handbook/cases/jev/) |

> 代码审查、缺陷检测、补丁交付、人机协作；Vibe Designing、GenUI 设计范式；汽车/零售/企业 IT 智能运维；长周期记忆、内容洞察、Data Agent；世界 AI 开源大赛优秀作品；Jev 模型解析与智能路由。

### 🔭 总结与展望

| 章节 | 📝 源文件 | 🌐 阅读站 |
| --- | --- | --- |
| 第 30 章 · 从 Agentic Application 到 Agentic OS | [GitHub](<./07-conclusion/第 30 章 从 Agentic Application 到 Agentic OS.md>) | [阅读站](https://aliyun.github.io/ai-agent-handbook/outlook/chapter-30.html) |

> 从单个应用走向可协作、可治理、可持续演进的智能系统。

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 推荐阅读路径

> 以下路径均链接到 **🌐 阅读站**（最佳阅读体验）。各章 📝 源文件见上方[章节导航](#章节导航)。

### 🟢 第一次系统了解企业 Agent

> 先建立全貌认知与架构视图，再深入构建与治理。适合首次系统学习。

[📊 调研报告](https://aliyun.github.io/ai-agent-handbook/survey.html) → [第 1 章 · AI 原生应用的新阶段](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-01.html) → [第 2 章 · Agentic Application 参考架构](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-02.html) → [第 3 章 · Harness 主流构建方式](https://aliyun.github.io/ai-agent-handbook/build/chapter-03.html) → [第 4 章 · 任务编排与长程推进](https://aliyun.github.io/ai-agent-handbook/build/chapter-04.html) → [第 5 章 · 上下文、状态与能力资产](https://aliyun.github.io/ai-agent-handbook/build/chapter-05.html) → [第 6 章 · 受控执行与验证反馈](https://aliyun.github.io/ai-agent-handbook/build/chapter-06.html) → [第 13 章 · Agent 可观测性](https://aliyun.github.io/ai-agent-handbook/governance/chapter-13.html) → [第 14 章 · Agent 安全](https://aliyun.github.io/ai-agent-handbook/governance/chapter-14.html) → [第 15 章 · AI 资产发现与管理](https://aliyun.github.io/ai-agent-handbook/governance/chapter-15.html) → [第 16 章 · 行为生成与质量验证](https://aliyun.github.io/ai-agent-handbook/governance/chapter-16.html)

### 🔵 正在把 Agent 接入生产

> 聚焦运行时基础设施、安全治理与持续优化，面向已在生产环境部署 Agent 的团队。

[第 7 章 · 运行时与沙箱](https://aliyun.github.io/ai-agent-handbook/run/chapter-07.html) → [第 8 章 · 状态存储与语义资产](https://aliyun.github.io/ai-agent-handbook/run/chapter-08.html) → [第 9 章 · AI 网关与流量治理](https://aliyun.github.io/ai-agent-handbook/run/chapter-09.html) → [第 13 章 · 可观测性](https://aliyun.github.io/ai-agent-handbook/governance/chapter-13.html) → [第 14 章 · Agent 安全](https://aliyun.github.io/ai-agent-handbook/governance/chapter-14.html) → [第 18 章 · Agent 调优总览](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-18.html) → [第 19 章 · 轨迹数据](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-19.html) → [第 20 章 · 运行时数据处理](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-20.html) → [第 21 章 · 黄金数据集](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-21.html) → [第 22 章 · Badcase 优化](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-22.html) → [第 23 章 · 受控自进化](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-23.html)

### 🟣 正在建设多 Agent 系统

> 从任务边界、委派与通信入手，建立可协作的多 Agent 体系。

[第 4 章 · 任务编排与长程推进](https://aliyun.github.io/ai-agent-handbook/build/chapter-04.html) → [第 5 章 · 上下文、状态与能力资产](https://aliyun.github.io/ai-agent-handbook/build/chapter-05.html) → [第 6 章 · 受控执行与验证反馈](https://aliyun.github.io/ai-agent-handbook/build/chapter-06.html) → [第 10 章 · 异步任务与自动化](https://aliyun.github.io/ai-agent-handbook/run/chapter-10.html) → [第 11 章 · Multi-Agent 协作](https://aliyun.github.io/ai-agent-handbook/run/chapter-11.html) → [第 12 章 · 分布式通信](https://aliyun.github.io/ai-agent-handbook/run/chapter-12.html) → [第 13 章 · 可观测性](https://aliyun.github.io/ai-agent-handbook/governance/chapter-13.html) → [第 16 章 · 行为生成与质量验证](https://aliyun.github.io/ai-agent-handbook/governance/chapter-16.html)

### 🟠 负责评估与持续优化

> 建立从运行事实到能力提升的数据飞轮。

[第 13 章 · 可观测性](https://aliyun.github.io/ai-agent-handbook/governance/chapter-13.html) → [第 18 章 · Agent 调优总览](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-18.html) → [第 19 章 · 轨迹数据](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-19.html) → [第 20 章 · 运行时数据处理](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-20.html) → [第 21 章 · 黄金数据集](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-21.html) → [第 22 章 · Badcase 优化](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-22.html) → [第 23 章 · 受控自进化](https://aliyun.github.io/ai-agent-handbook/optimization/chapter-23.html) → [🏭 相关实践案例](https://aliyun.github.io/ai-agent-handbook/cases/)

### 🔴 负责选型或项目立项

> 快速建立战略判断，理解投入边界与长期演进方向。

[📊 调研报告](https://aliyun.github.io/ai-agent-handbook/survey.html) → [第 1 章 · AI 原生应用的新阶段](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-01.html) → [第 2 章 · Agentic Application 参考架构](https://aliyun.github.io/ai-agent-handbook/architecture/chapter-02.html) → [第 3 章 · Harness 构建范式](https://aliyun.github.io/ai-agent-handbook/build/chapter-03.html) → [🏭 实践篇 · 全部案例](https://aliyun.github.io/ai-agent-handbook/cases/) → [第 30 章 · Agentic OS](https://aliyun.github.io/ai-agent-handbook/outlook/chapter-30.html)

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 实践案例速览

> 以下为各章案例的快速索引。案例链接均指向 **🌐 阅读站**，源文件路径见上方[章节导航](#章节导航)中对应章节目录。

<details>
<summary><strong>第 25 章 · 研发效能（7 个案例）</strong></summary>

- [ABACI — 内核补丁定向测试与缺陷检测智能体](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/abaci.html)
- [Kitta — 领域专用 Code Review Agent](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/kitta.html)
- [PatchPilot Agents — 可编排的内核补丁交付闭环](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/patchpilot.html)
- [从报警到自动修复 — PolarDB-X 的 Loop 工程实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/polardb-x.html)
- [从编码提效到端到端交付 — 云通信的人机协作实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/cloud-communications.html)
- [从评测驱动到端到端交付 — AI Agent 安全产品研发提效](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/security-engineering.html)
- [多 Agent 组成研发小队 — 从写代码走向端到端交付](https://aliyun.github.io/ai-agent-handbook/cases/chapter-25/engineering-team.html)

</details>

<details>
<summary><strong>第 26 章 · 设计工程（2 个案例）</strong></summary>

- [GenUI — 让 Agent 从给出答案走向交付结果](https://aliyun.github.io/ai-agent-handbook/cases/chapter-26/genui.html)
- [Vibe Designing — 意图驱动的 AI 设计范式进化](https://aliyun.github.io/ai-agent-handbook/cases/chapter-26/vibe-designing.html)

</details>

<details>
<summary><strong>第 27 章 · 运维、安全与企业 IT（3 个案例）</strong></summary>

- [吉利汽车智能运维的落地实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-27/geely.html)
- [塔斯汀万店连锁的智能运维闭环实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-27/tastien.html)
- [畅捷通的可观测与智能运维实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-27/chanjet.html)

</details>

<details>
<summary><strong>第 28 章 · 客户、销售与运营（4 个案例）</strong></summary>

- [MiniMax — 海量长周期记忆数据底座实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-28/minimax.html)
- [信永中和会计师事务所的办公提效探索](https://aliyun.github.io/ai-agent-handbook/cases/chapter-28/shinewing.html)
- [哔哩哔哩构建全域内容洞察的实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-28/bilibili.html)
- [运营分析 Data Agent 实践](https://aliyun.github.io/ai-agent-handbook/cases/chapter-28/data-agent.html)

</details>

<details>
<summary><strong>Jev 专题 · 结构化决策实践（2 篇）</strong></summary>

- [深度解析 Jev 模型 — 如何快速做结构化决策](https://aliyun.github.io/ai-agent-handbook/cases/jev/deep-dive.html)
- [HiRoute — Jev 模型智能路由实践](https://aliyun.github.io/ai-agent-handbook/cases/jev/hiroute.html)

</details>

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 下一步规划

白皮书将以开放项目的方式持续维护，而不是在首次发布后封存。接下来的重点包括：

- **扩展企业实践案例**：增加更多来自研发、运营、客服、数据、安全、财务和行业场景的一线案例，补充成功路径、架构取舍与真实失败模式。
- **增加云资源线上体验**：围绕沙箱、Runtime、AI 网关、状态存储、可观测和评估等关键能力，设计可复现的云上体验流程，让读者从阅读进一步走向动手验证。
- **持续完善治理内容**：跟进身份权限、Prompt Injection 防护、数据出域、审计、资产注册、版本治理和上线前仿真等企业核心议题。
- **持续完善评估体系**：补充任务成功率、轨迹评估、LLM-as-Judge、黄金数据集、Badcase 回归、线上实验和成本质量权衡等方法与案例。
- **跟进技术演进**：持续吸收模型、Harness、协议、Runtime、多 Agent 和 Agentic OS 的新进展，并及时修正已经不再适用的判断。
- **建设社区协作机制**：逐步完善内容规范、案例模板、术语表、校对流程和版本发布方式，降低高质量贡献的门槛。

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 参与共建

欢迎开发者、架构师、研究者、企业技术团队和产品实践者参与共建。你可以：

- 提交 [Issue](https://github.com/aliyun/ai-agent-handbook/issues)，指出事实错误、概念歧义、链接失效或需要补充的主题；
- 提交 [Pull Request](https://github.com/aliyun/ai-agent-handbook/pulls)，完善章节、修正内容、优化图表或补充参考资料；
- 分享经过脱敏的企业实践、故障复盘、评估方法与架构取舍；
- 提供可复现的代码、云资源体验流程、数据集或实验方案；
- 参与术语统一、技术审校、案例评审和内容翻译。

贡献内容应尊重原创与授权边界；涉及企业数据、客户信息、内部系统和安全细节时，请先完成必要的脱敏与许可确认。

> 💬 欢迎加入[共读交流群](./共读微信群.md)，与更多同行者一起讨论。

<p align="right"><sub><a href="#目录">↑ 回到目录</a></sub></p>

---

## 贡献者

感谢所有参与架构设计、章节写作、案例整理与内容审校的贡献者。

### 阿里云

| 篇章 | 贡献者 |
| --- | --- |
| 前言 | 麻芃 |
| 开发者调查报告 | 任娟、王晨 |
| 架构篇 | 王晨、刘军、沈林 |
| 构建篇 | 刘军、泮圣伟、王晨 |
| 运行篇 | 赵庆杰、李诗波、林清山、黄晓萌、张添翼、赵源筱、孙校、宋震、胡庆达、柳遵飞、朱桐、余华峰、罗鑫、孔可青 |
| 治理篇 | 肖长军、周洋、张磊、王方、张海彬、程书意、刘子明、饶子昊、任懿、杨永、王硕、马昕、刘宇轩、杨翊 |
| 调优篇 | 张寒萌、李盛荣、王亚宁、孙坚运、马云雷、王桢、郑前祎、刘航、陈新 |
| 实践篇 | 杨涛、朱颜、余艾琳、胡峻、姜剑、张添翼 |
| 总结与展望篇 | 林演 |

### 外部贡献者

项目持续开放社区贡献，欢迎开发者、架构师、研究者、企业技术团队和产品实践者通过 [Issue](https://github.com/aliyun/ai-agent-handbook/issues) 或 [Pull Request](https://github.com/aliyun/ai-agent-handbook/pulls) 参与内容共建；贡献被采纳后，贡献者信息将补充到本模块。

---

如果这份白皮书可以帮助您更好地理解、构建、运行、治理和调优 Agent，欢迎 [⭐ Star](https://github.com/aliyun/ai-agent-handbook)、分享、讨论并参与共建。