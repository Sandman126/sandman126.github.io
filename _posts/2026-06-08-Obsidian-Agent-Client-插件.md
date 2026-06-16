---
title: Obsidian Agent Client 插件
date: '2026-06-08'
tags:
- obsidian
- AI
- agent
- plugin
categories:
- 技术
- AI
description: Agent Client Plugin for Obsidian — 在 Obsidian 中直接使用 AI 智能体（Claude Code、Codex、Gemini
  CLI 等）
source: https://github.com/RAIT-09/obsidian-agent-client
summary: Agent Client 是一款 Obsidian 插件，基于 Agent Client Protocol (ACP) 协议，将 Claude Code、Codex、Gemini
  CLI 等 AI 智能体直接集成到 Obsidian 中。
---

# Obsidian Agent Client 插件

[GitHub](https://github.com/RAIT-09/obsidian-agent-client) | [Obsidian 社区](https://community.obsidian.md/plugins/agent-client)

> 基于 [Agent Client Protocol (ACP)](https://github.com/agentclientprotocol/agent-client-protocol) 协议（由 Zed 开发），将 AI 智能体（Claude Code、Codex、Gemini CLI）直接带入 Obsidian，在你的知识库中与 AI 助手直接对话。

## 功能特性

- **笔记引用**：使用 `@笔记名` 语法引用你的笔记
- **图片附件**：将图片粘贴或拖拽到聊天中
- **斜杠命令**：使用 AI 智能体提供的 `/` 命令
- **多智能体支持**：在 Claude Code、Codex、Gemini CLI 和自定义智能体之间切换
- **多会话**：在独立视图中同时运行多个智能体
- **浮动聊天**：持久可折叠的聊天窗口，方便快速访问
- **模式与模型切换**：在聊天中切换 AI 模型和智能体模式
- **会话历史**：恢复或分叉之前的对话
- **聊天导出**：将对话保存为 Markdown 笔记
- **终端集成**：让智能体执行命令并返回结果
- **MCP 支持**：智能体使用其已配置的 MCP 服务器，无需在插件中进行额外设置

## 安装方法

### 社区插件安装
1. 打开 **设置 → 社区插件 → 浏览**
2. 搜索 **"Agent Client"**
3. 点击 **安装**，然后 **启用**

### 通过 BRAT 安装（预发布版本）

想在正式发布到社区插件前尝鲜预发布版本：

1. 安装 [BRAT](https://github.com/TfTHacker/obsidian42-brat) 插件
2. 进入 **设置 → BRAT → 添加 Beta 插件**
3. 粘贴：`https://github.com/RAIT-09/obsidian-agent-client`
4. 从插件列表中启用 **Agent Client**

### 手动安装
1. 从 [Releases 页面](https://github.com/RAIT-09/obsidian-agent-client/releases) 下载 `main.js`、`manifest.json`、`styles.css`
2. 放入 `Vault文件夹/.obsidian/plugins/agent-client/`
3. 在 **设置 → 社区插件** 中启用该插件

## 快速开始

打开终端（macOS/Linux 使用 Terminal，Windows 使用 PowerShell）并运行以下命令。

### 1. 安装智能体及 ACP 适配器（以 Claude Code 为例）
```bash
curl -fsSL https://claude.ai/install.sh | bash   # 安装 Claude Code
npm install -g @agentclientprotocol/claude-agent-acp   # 安装 ACP 适配器
```

### 2. 登录（如果使用 API 密钥可跳过）
```bash
claude
```
按照提示使用 Anthropic 账户进行身份验证。

### 3. 查找路径
```bash
which node       # macOS/Linux
which claude-agent-acp
where.exe node   # Windows
where.exe claude-agent-acp
```

### 4. 配置 **设置 → Agent Client**
- **Node.js 路径**：例如 `/usr/local/bin/node`
- **内置智能体 → Claude Code → 路径**：例如 `/usr/local/bin/claude-agent-acp`（注意不是 `claude`）
- **API 密钥**：添加你的密钥，如果已通过 CLI 登录则留空

### 5. 开始对话
点击侧边栏中的机器人图标开始聊天。

### 设置指南
- [Claude Code 设置](https://rait-09.github.io/obsidian-agent-client/agent-setup/claude-code.html)
- [Codex 设置](https://rait-09.github.io/obsidian-agent-client/agent-setup/codex.html)
- [Gemini CLI 设置](https://rait-09.github.io/obsidian-agent-client/agent-setup/gemini-cli.html)
- [自定义智能体设置](https://rait-09.github.io/obsidian-agent-client/agent-setup/custom-agents.html)（OpenCode、Qwen Code、Kiro、Mistral Vibe 等）

**[完整文档](https://rait-09.github.io/obsidian-agent-client/)**

## 开发

```bash
npm install
npm run dev
```

生产构建：

```bash
npm run build
```

## 许可协议

Apache License 2.0 — 详见 [LICENSE](https://github.com/RAIT-09/obsidian-agent-client/blob/master/LICENSE)。
