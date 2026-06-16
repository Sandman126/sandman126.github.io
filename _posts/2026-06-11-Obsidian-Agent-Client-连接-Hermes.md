---
title: Obsidian Agent Client 连接 Hermes
date: '2026-06-11'
tags:
- obsidian
- hermes
- acp
- wsl
categories:
- 技术
- AI
description: Obsidian Agent Client 插件通过 ACP 连接 WSL 中的 Hermes Agent
source: https://github.com/RAIT-09/obsidian-agent-client
summary: 通过 wsl.exe 桥接，在 Obsidian 中直接与 Hermes 对话
image: /assets/img/img-cyber-connect.jpeg
---


# Obsidian Agent Client 连接 Hermes

[Agent Client](https://github.com/RAIT-09/obsidian-agent-client) 是 Obsidian 社区插件，通过 ACP (Agent Client Protocol) 连接 AI 代理。Hermes 内置 ACP 支持（`hermes acp`），可以在 Obsidian 中直接与 Hermes 对话。

## 原理

- Obsidian 运行在 **Windows 原生环境**
- Hermes 运行在 **WSL** 内
- 通过 `wsl.exe` 桥接：Obsidian 插件启动 `wsl.exe hermes acp` 作为子进程
- ACP 使用 stdio JSON-RPC 通信

## 配置步骤

### 1. 安装插件

- 打开 Obsidian → 设置 → 社区插件 → 浏览
- 搜索 **"Agent Client"**，点击安装并启用

### 2. 添加 Hermes 为自定义 Agent

打开 **设置 → Agent Client → Custom Agents**，点击 **Add custom agent**，填写：

| 字段 | 值 |
|------|-----|
| Agent ID | `hermes` |
| Display name | `Hermes Agent` |
| Path | `wsl.exe` |
| Arguments | `~/.local/bin/hermes` |
| | `acp` |

Arguments 区域每行一个参数，共两行：

```
~/.local/bin/hermes
acp
```

### 3. 验证桥接

在 Windows PowerShell 或 CMD 中测试：

```powershell
wsl.exe ~/.local/bin/hermes acp --version
```

应输出版本号（如 `0.16.0`）。

### 4. 使用

- 点击左侧 Ribbon 栏的机器人图标
- 在聊天头部的 Agent 下拉菜单中选择 **Hermes Agent**
- 发送消息即可与 Hermes 对话

## 备选配置

如果 `~` 在 Windows 中无法解析为 WSL 家目录，改用完整路径：

| 字段 | 值 |
|------|-----|
| Path | `wsl.exe` |
| Arguments | `/home/liron/.local/bin/hermes` |
| | `acp` |

或者用 bash login shell 包装：

| 字段 | 值 |
|------|-----|
| Path | `wsl.exe` |
| Arguments | `bash` |
| | `-l` |
| | `-c` |
| | `hermes acp` |

## 注意事项

- 插件会自动管理 `hermes acp` 的生命周期，无需手动后台启动
- 换模型/API key 时，在 WSL 内用 `hermes model` 或 `hermes config set` 修改
- 首次启动可能出现 `rtk` 警告（`rtk binary not found in PATH`），这是装饰性的，不影响 ACP 功能

## 相关链接

- [Agent Client 插件 GitHub](https://github.com/RAIT-09/obsidian-agent-client)
- [自定义 Agent 配置文档](https://rait-09.github.io/obsidian-agent-client/agent-setup/custom-agents.html)
- [Hermes ACP 文档](https://hermes-agent.nousresearch.com/docs)
