---
title: Awesome Hermes Agent 生态资源列表
date: '2026-05-28'
tags:
  - hermes
  - awesome-list
  - 资源列表
  - 社区资源
  - plugins
categories:
  - AI
  - 技术
description: 由 0xNyk 整理的 Hermes Agent 生态资源合集，涵盖技能、插件、工具、集成、部署、多智能体等
source: https://github.com/0xNyk/awesome-hermes-agent
summary: 一个精心策划的 Hermes Agent 生态资源列表，包含社区技能、插件、工具、集成、多智能体框架、领域应用、部署方案等
image: /assets/img/img-opensource-code.jpeg
---
19|
20|# Awesome Hermes Agent 生态资源列表
21|
22|> 来源：[github.com/0xNyk/awesome-hermes-agent](https://github.com/0xNyk/awesome-hermes-agent)
23|> 标签：`production` — 稳定可靠；`beta` — 可用但演化中；`experimental` — 早期概念验证
24|
25|---
26|
27|## 🚀 新手三步入門
28|
29|1. **快速上手** — [官方文档](https://hermes-agent.nousresearch.com/docs/)
30|2. **安装社区技能** — [wondelai/skills](https://github.com/wondelai/skills)（380+ ⭐，跨平台技能库）
31|3. **配置 GUI** — [hermes-workspace](https://github.com/outsourc-e/hermes-workspace)（500+ ⭐）或 [mission-control](https://github.com/builderz-labs/mission-control)（3.7k+ ⭐）
32|
33|---
34|
35|## 📦 社区技能
36|
37|| 名称 | 说明 | 成熟度 |
38||------|------|--------|
39|| [hermes-plugins](https://github.com/42-evey/hermes-plugins) | 目标管理、智能体间桥接、模型选择、成本控制 | beta |
40|| [hermes-skill-factory](https://github.com/Romanescu11/hermes-skill-factory) | 从工作流自动生成可复用技能 | beta |
41|| [litprog-skill](https://github.com/tlehman/litprog-skill) | 跨平台文字编程（Hermes/Claude Code/OpenCode） | beta |
42|| [hermes-life-os](https://github.com/Lethe044/hermes-life-os) | 个人生活 OS，学习日常模式 | experimental |
43|| [hermes-incident-commander](https://github.com/Lethe044/hermes-incident-commander) | 自治 SRE 事故检测与自愈 | beta |
44|| [hermes-dojo](https://github.com/Yonkoo11/hermes-dojo) | 监控性能 → 识别弱技能 → 自动迭代改进 | beta |
45|| [hermes-spotify-skill](https://github.com/Alexeyisme/hermes-spotify-skill) | 无头 Linux / Raspberry Pi 的 Spotify 播放控制 | beta |
46|| [oh-my-hermes](https://github.com/witt3rd/oh-my-hermes) | 多智能体编排套件（deep-research、autopilot、triage 等） | beta |
47|| [hermes-nextcloud](https://github.com/adnw-vinc/hermes-nextcloud) | 自托管 Nextcloud（WebDAV、Notes、CalDAV、CardDAV） | beta |
48|| [acca-tracker](https://github.com/svenmedina07-ship-it/skills/tree/main/acca-tracker) | 多运动博彩单追踪（英超、NBA 等，30+ 投注类型） | beta |
49|
50|### agentskills.io 生态
51|
52|| 名称 | 说明 | 成熟度 |
53||------|------|--------|
54|| [wondelai/skills](https://github.com/wondelai/skills) | 跨平台技能库（Claude Code / Hermes / Codex 兼容） | production |
55|| [youtube-skills](https://github.com/ZeroPointRepo/youtube-skills) | YouTube 搜索 / 频道浏览 / 可靠字幕（解决 VPS 被封 IP） | production |
56|| [Anthropic-Cybersecurity-Skills](https://github.com/mukul975/Anthropic-Cybersecurity-Skills) | 753+ 网络安全技能，映射 MITRE ATT&CK，4k+ ⭐ | production |
57|| [chainlink-agent-skills](https://github.com/smartcontractkit/chainlink-agent-skills) | Chainlink 预言机数据、CCIP、智能合约交互 | production |
58|| [black-forest-labs/skills](https://github.com/black-forest-labs/skills) | FLUX 模型官方图像生成技能 | production |
59|| [drawio-skill](https://github.com/Agents365-ai/drawio-skill) | 自然语言生成 draw.io 图表，1.1k+ ⭐ | production |
60|| [open-design](https://github.com/nexu-io/open-design) | 开源 Claude Design 替代，129 个设计系统，28k ⭐ | production |
61|| [AgentCash](https://github.com/Merit-Systems/agentcash-skills) | 300+ 高级 API + 钱包支付（x402 / MPP） | beta |
62|| [master-skill](https://github.com/voidborne-d/master-skill) | 5 阶段研究-综合管道 → 浓缩行业认知为便携技能包 | beta |
63|
64|---
65|
66|## 🔌 插件
67|
68|| 名称 | 说明 | 成熟度 |
69||------|------|--------|
70|| [rtk-hermes](https://github.com/ogallotti/rtk-hermes) | 拦截 shell 输出压缩，减少 60-90% token | beta |
71|| [plur](https://github.com/plur-ai/plur) | 共享记忆层，YAML 开放 engram 格式 | beta |
72|| [hermes-web-search-plus](https://github.com/robbyczgw-cla/hermes-web-search-plus) | 多提供商智能搜索路由（Serper/Tavily/Exa 等） | beta |
73|| [hermes-weather-plugin](https://github.com/FahrenheitResearch/hermes-weather-plugin) | 专业级天气（NWS 图、NEXRAD 雷达、气象计算） | beta |
74|| [hermes-curator-evolver](https://github.com/pingchesu/hermes-curator-evolver) | v0.12 Curator 增强版，证据驱动，SQLite 追踪 | beta |
75|| [agent-analytics-hermes-plugin](https://github.com/Agent-Analytics/agent-analytics-hermes-plugin) | Hermes WebUI 原生 Signals 分析仪表盘页 | beta |
76|| [evey-bridge-plugin](https://github.com/42-evey/evey-bridge-plugin) | Claude Code ↔ Hermes 桥接 | beta |
77|
78|---
79|
80|## 🛠️ 工具与仪表盘
81|
82|| 名称 | 说明 | 成熟度 |
83||------|------|--------|
84|| [hermes-workspace](https://github.com/outsourc-e/hermes-workspace) | 最完整 Web GUI（聊天/终端/记忆/技能管理） | production |
85|| [hermes-web-ui](https://github.com/EKKOLearnAI/hermes-web-ui) | Vue 3 + TypeScript 仪表盘，Token 分析，3.6k ⭐ | production |
86|| [mission-control](https://github.com/builderz-labs/mission-control) | 多智能体舰队管理/成本追踪，3.7k ⭐ | production |
87|| [SkillClaw](https://github.com/AMAP-ML/SkillClaw) | 自动进化/去重/改进技能库，705 ⭐ | production |
88|| [camofox-browser](https://github.com/jo-inc/camofox-browser) | 隐身浏览器规避 Cloudflare / 反爬，4k ⭐ | production |
89|| [hermes-desktop](https://github.com/dodo-reach/hermes-desktop) | 原生 macOS 工作区（SSH 直连、嵌入终端） | beta |
90|| [hermes-ui](https://github.com/pyrate-llama/hermes-ui) | 单文件玻璃拟态 Web UI，SSE 流式 | beta |
91|| [Clarvia](https://github.com/clarvia-project/scanner) | AEO 评分，分析 15,400+ MCP 服务器对智能体的友好度 | production |
92|| [agenttrace](https://github.com/luoyuctl/agenttrace) | 本地 TUI 会话审计（成本/Token 峰值/工具失败/健康分） | beta |
93|| [nix-hermes-agent](https://github.com/0xrsydn/nix-hermes-agent) | 可复现 Nix 部署 | beta |
94|
95|---
96|
97|## 🧠 记忆系统
98|
99|| 名称 | 说明 | 成熟度 |
100||------|------|--------|
101|| [Mnemosyne](https://github.com/AxDSan/Mnemosyne) | SQLite + 向量混合搜索，亚毫秒级，时空知识图谱 | beta |
102|| [mnemo-hermes](https://github.com/eleion-ai/mnemo-hermes) | Ollama 本地 pgvector 语义记忆，免 API Key | beta |
103|| [hindsight](https://github.com/vectorize-io/hindsight) | 长期记忆层（语义/图谱/时序检索） | production |
104|| [flowstate-qmd](https://github.com/amanning3390/flowstate-qmd) | RAG + 向量搜索预取上下文 | beta |
105|
106|---
107|
108|## 🔗 集成与桥接
109|
110|| 名称 | 说明 | 成熟度 |
111||------|------|--------|
112|| [hermes-android](https://github.com/raulvidis/hermes-android) | Android 设备控制（完整 Python 工具集） | beta |
113|| [microsoft-workspace-skill](https://github.com/Andrew-Girgis/microsoft-workspace-skill) | Outlook/Hotmail/365 全功能集成（OAuth2） | beta |
114|| [hermes-agent-acp-skill](https://github.com/Rainhoole/hermes-agent-acp-skill) | 多智能体路由（Codex / Claude Code） | beta |
115|| [agent-android](https://github.com/aivanelabs/ai-rpa/tree/main/skills/agent-android) | LAN 内 Android 控制（WiFi，无 ADB/root） | beta |
116|| [MeiGen-AI-Design-MCP](https://github.com/jau123/MeiGen-AI-Design-MCP) | 9 种图像/视频生成模型 + 本地 ComfyUI，1k ⭐ | production |
117|| [mistral-mcp](https://github.com/Swih/mistral-mcp) | Mistral AI 全套（OCR/音频/Codestral/分类），22 工具 | beta |
118|
119|---
120|
121|## 🌐 多智能体与蜂群
122|
123|- **[Ankh.md](https://github.com/Abruptive/Ankh.md)** — TAW Agent x Hermes 蜂群框架（experimental）
124|- **[bigiron](https://github.com/supermodeltools/bigiron)** — AI SDLC，Hermes + Supermodel 代码图（beta）
125|- **[opencode-hermes-multiagent](https://github.com/1ilkhamov/opencode-hermes-multiagent)** — 17 个专业角色智能体（beta）
126|
127|---
128|
129|## 🎯 领域应用
130|
131|- **Minecraft** — [hermescraft](https://github.com/bigph00t/hermescraft)：持久记忆的 AI 伙伴
132|- **机器人** — [hermes-embodied](https://github.com/bryercowan/hermes-embodied)：VLA 模型微调
133|- **火星车** — [Hermes-mars-rover](https://github.com/Snehal707/Hermes-mars-rover)：ROS2 + Gazebo 模拟
134|- **动漫** — [anihermes](https://github.com/rodmarkun/anihermes)：本地动漫服务器 + 追踪
135|- **求职** — [job-scout-agent](https://github.com/Christabel337/job-scout-agent)：自主求职代理
136|- **法律** — [hermes-legal](https://github.com/Lethe044/hermes-legal)：合同风险分析（英/土）
137|- **创业** — [hermes-startup-architect](https://github.com/dlkakbs/hermes-startup-architect)：自动生成投资者套件
138|- **区块链** — [mercury](https://github.com/hxsteric/mercury)：多链现金流分析
139|
140|---
141|
142|## 🧬 衍生与分支
143|
144|- [hermes-agent-camel](https://github.com/nativ3ai/hermes-agent-camel) — 集成 CaMeL 信任边界（beta）
145|- [hermes-alpha](https://github.com/kaminocorp/hermes-alpha) — 预配云部署（beta）
146|
147|---
148|
149|## 💡 升级蓝图精选
150|
151|**记忆栈分层**：内置记忆 → Honcho（跨会话）→ Hindsight（长程检索）→ Plur（便携共享记忆）
152|
153|**自进化+安全网**：hermes-agent-self-evolution + lintlang + 回归检查，防止静默退化
154|
155|**多智能体执行层**：Hermes 核心委派 + ACP 路由 + 本地执行器桥接 + 专业角色
156|
157|---
158|
159|*笔记创建于：2026-05-28*
160|
