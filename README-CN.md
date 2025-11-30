<div align="center">

<img src="https://img.shields.io/badge/-AutoAgents-000000?style=for-the-badge&labelColor=faf9f6&color=faf9f6&logoColor=000000" alt="AutoAgents" width="320"/>

<h4>Python AI 智能体框架 - Monorepo</h4>

[English](README.md) | **简体中文**

<a href="https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Python">
  <img alt="GitHub version" src="https://img.shields.io/badge/version-0.0.1-blue.svg?style=for-the-badge" />
</a>
<a href="LICENSE">
  <img alt="License MIT" src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" />
</a>

</div>

**AutoAgents-Python** 是一个全面的基于 Python 的 AI 智能体框架生态系统，由四个模块化库组成，它们协同工作以提供强大的 AI 智能体能力。

## 📦 Monorepo 结构

本仓库包含四个主要库：

```
AutoAgents-Python/
├── libs/
│   ├── core/                # 🎯 核心库 - 聊天、知识库、数据科学等
│   │   ├── src/             # 核心实现
│   │   ├── playground/      # 示例脚本和测试
│   │   ├── pyproject.toml   # 包配置
│   │   └── README.md        # 核心文档
│   │
│   ├── agentspro/           # 🔧 AgentsPro - 文本到智能体转换
│   │   ├── src/             # AgentsPro 实现
│   │   ├── pyproject.toml   # 包配置
│   │   └── README.md        # AgentsPro 文档
│   │
│   ├── graph/               # 🔄 图引擎 - 智能体工作流编排
│   │   ├── src/             # 图引擎实现
│   │   ├── playground/      # 示例工作流
│   │   ├── pyproject.toml   # 包配置
│   │   └── README.md        # 图引擎文档
│   │
│   └── cua/                 # 🌐 计算机使用智能体 - 浏览器与 UI 自动化
│       ├── src/             # CUA 实现
│       ├── playground/      # 示例自动化
│       ├── pyproject.toml   # 包配置
│       └── README.md        # CUA 文档
│
├── .gitignore              # 统一的 gitignore
├── LICENSE                 # MIT 许可证
└── README.md               # 本文件
```

## 🎯 核心库 (Core)

**基础 AI 智能体能力**

核心库提供构建 AI 智能体的基本功能：

- 💬 **聊天客户端**：多模型 LLM 聊天接口
- 📚 **知识库**：用于 RAG 应用的向量数据库
- 🕷️ **爬虫客户端**：网页抓取和数据提取
- 🔧 **MCP 集成**：模型上下文协议支持
- 📊 **数据科学智能体**：自动化数据分析和可视化
- 🎨 **幻灯片生成**：PPT 创建和操作

📖 **文档**: [libs/core/README.md](libs/core/README.md)

## 🔧 AgentsPro

**文本到智能体转换框架**

AgentsPro 能够将自然语言描述转换为可执行的智能体工作流：

- 📝 文本到工作流转换
- 🔄 与 Dify 和 Agentify 集成
- 🎯 流程图解释

📖 **文档**: [libs/agentspro/README.md](libs/agentspro/README.md)

## 🔄 图引擎 (Graph)

**智能体工作流编排**

图引擎为复杂的多智能体系统提供强大的工作流编排：

- 🔄 基于状态的工作流执行
- 🔀 并行和条件分支
- 🔁 循环和迭代支持
- 📊 可视化工作流设计
- 🔧 与 Dify 和 Agentify 格式集成

📖 **文档**: [libs/graph/README.md](libs/graph/README.md)

## 🌐 计算机使用智能体 (CUA)

**浏览器与 UI 自动化框架**

CUA 提供全面的浏览器自动化和计算机控制能力：

- 🌐 **浏览器智能体**：使用 AI 进行 Web 自动化
- 🖥️ **计算机智能体**：桌面应用程序控制
- 📱 **移动智能体**：移动应用自动化
- 🔐 **验证码解决器**：自动化验证码解决
- 🎯 **预构建智能体**：登录、搜索等

📖 **文档**: [libs/cua/README.md](libs/cua/README.md)

## 🚀 快速开始

### 前置要求

- **Python**: 3.10 或更高版本
- **pip**: 最新版本

### 安装

每个库可以独立安装：

```bash
# 安装核心库
cd libs/core
pip install -e .

# 安装 AgentsPro
cd ../agentspro
pip install -e .

# 安装图引擎
cd ../graph
pip install -e .

# 安装 CUA
cd ../cua
pip install -e .
```

### 基础用法

**核心库 - 聊天示例**:
```python
from autoagents_core.client import ChatClient

client = ChatClient(api_url="YOUR_API_URL", api_key="YOUR_API_KEY")
response = client.send_message("你好，AI！")
print(response)
```

**图引擎 - 工作流示例**:
```python
from autoagents_graph.engine import GraphEngine

engine = GraphEngine()
workflow = engine.load_workflow("path/to/workflow.yaml")
result = await engine.execute(workflow, inputs={"query": "test"})
```

**CUA - 浏览器自动化示例**:
```python
from autoagents_cua.agent import BrowserAgent

agent = BrowserAgent()
await agent.navigate("https://example.com")
await agent.click("button[type='submit']")
```

## 🏗️ 架构概览

```
┌─────────────────────────────────────────────────────────┐
│                      应用层                              │
│  - 自定义 AI 智能体                                      │
│  - 业务逻辑                                              │
└─────────────────────────────────────────────────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│                  AutoAgents 库                          │
├─────────────┬──────────────┬──────────────┬────────────┤
│    Core     │  AgentsPro   │    Graph     │    CUA     │
│  (客户端)   │ (文本转智能) │  (工作流)    │  (浏览器)  │
└─────────────┴──────────────┴──────────────┴────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│              外部服务与 API                              │
│  - LLM 提供商 (OpenAI、Anthropic 等)                    │
│  - 向量数据库 (Supabase 等)                             │
│  - 浏览器引擎 (Playwright、Selenium)                    │
└─────────────────────────────────────────────────────────┘
```

## 📚 文档

每个库都有其详细的文档：

- **Core**: [libs/core/README.md](libs/core/README.md)
- **AgentsPro**: [libs/agentspro/README.md](libs/agentspro/README.md)
- **Graph**: [libs/graph/README.md](libs/graph/README.md)
- **CUA**: [libs/cua/README.md](libs/cua/README.md)

## 🤝 贡献

我们欢迎对任何库的贡献！请遵循以下指南：

1. **Fork** 仓库
2. **创建**功能分支 (`git checkout -b feature/amazing-feature`)
3. **遵循** Python 最佳实践和类型提示
4. **彻底测试**您的更改
5. **提交**使用约定式提交 (`feat:`, `fix:`, `docs:` 等)
6. **推送**并打开 Pull Request

### 开发指南

- Python 3.10+ 带类型提示
- 遵循 PEP 8 风格指南
- 使用 Pydantic 进行数据验证
- 为新功能编写单元测试
- 根据需要更新文档

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

所有库（`core`、`agentspro`、`graph`、`cua`）都采用 MIT 许可证。

## 🔗 相关项目

- **AutoAgents-Core-Python**: https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python
- **AgentsPro-Python**: https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python
- **AutoAgents-Graph-Python**: https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python
- **AutoAgents-CUA-Python**: https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python

---

<div align="center">

由 [AutoAgents Algorithm Group](https://github.com/AutoAgents-Algorithm-Group) 用 ❤️ 制作

**如果觉得有用，请给个 Star ⭐！**

</div>
