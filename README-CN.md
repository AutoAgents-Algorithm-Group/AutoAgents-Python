<div align="center">

<img src="https://img.shields.io/badge/-Noma-000000?style=for-the-badge&labelColor=faf9f6&color=faf9f6&logoColor=000000" alt="Noma" width="320"/>

<h4>AI 智能体平台生态系统</h4>

[English](README.md) | **简体中文**

<a href="https://github.com/AutoAgents-Algorithm-Group/Noma">
  <img alt="GitHub version" src="https://img.shields.io/badge/version-0.0.1-blue.svg?style=for-the-badge" />
</a>
<a href="LICENSE">
  <img alt="License MIT" src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" />
</a>

</div>

Noma 是一个完整的 AI 智能体平台生态系统，包含用于 Web 自动化的**浏览器扩展**和用于用户管理和智能体编排的**着陆页/平台**。

## 📦 Monorepo 结构

本仓库包含两个主要项目：

```
Noma/
├── noma-extension/          # 🌐 浏览器扩展 (Chrome/Edge)
│   ├── src/                 # 扩展源代码
│   ├── backend/             # 可选的 Python AI 后端
│   └── README.md            # 扩展文档
│
├── noma-lp/                 # 🚀 着陆页与平台
│   ├── frontend/            # Next.js 网页应用
│   ├── backend/             # FastAPI 后端
│   ├── docker/              # Docker 部署
│   └── README.md            # 平台文档
│
├── .gitignore              # 统一的 gitignore
├── LICENSE                 # MIT 许可证
└── README.md               # 本文件
```

## 🌐 Noma Extension（浏览器扩展）

**Web 原生 AI 智能体平台，用于浏览器自动化**

一个 Chrome/Edge 扩展，使您能够直接在浏览器中创建和运行 AI 智能体，以自动化 Web 任务。

### 核心功能
- 🤖 **动作录制器**：记录 Web 交互并转换为自动化
- 🔧 **智能体构建器**：用于复杂自动化的可视化工作流编辑器
- 💬 **AI 聊天助手**：使用自然语言控制浏览器
- ⏰ **定时任务**：按计划自动运行智能体

### 快速开始

```bash
cd noma-extension
pnpm install
pnpm dev
# 在 Chrome 中加载 build/chrome-mv3-dev/
```

📖 **完整文档**: [noma-extension/README.md](noma-extension/README-CN.md)

## 🚀 Noma Platform（着陆页平台）

**全栈 AI 智能体管理平台**

一个用于管理用户、智能体和编排多智能体工作流的综合 Web 平台。

### 核心功能
- 🔐 **身份验证**：Better Auth 支持 GitHub OAuth
- 💬 **智能体对话**：与 AI 智能体实时流式对话
- 🔧 **MCP 集成**：模型上下文协议工具管理
- 📊 **深度研究**：多智能体研究工作流

### 技术栈
- **前端**: Next.js 16 + TypeScript + Shadcn/UI
- **后端**: FastAPI + LangChain + LangGraph
- **数据库**: PostgreSQL (Neon) + Drizzle ORM
- **身份验证**: Better Auth

### 快速开始

```bash
cd noma-lp

# 前端
cd frontend
npm install
npm run dev  # 运行在 http://localhost:3000

# 后端
cd ../backend
pip install -r requirements.txt
python -m uvicorn src.api.main:app --reload --port 8000
```

📖 **完整文档**: [noma-lp/README.md](noma-lp/README-CN.md)

## 🏗️ 架构概览

```
┌─────────────────────────────────────────────────────────┐
│                      用户界面                            │
├───────────────────┬─────────────────────────────────────┤
│    浏览器扩展      │       Web 平台 (Next.js)            │
│  (Noma Extension) │      (Noma Landing Page)           │
│  - 记录动作        │      - 用户管理                     │
│  - 构建工作流      │      - 智能体编排                   │
│  - 执行智能体      │      - 团队协作                     │
│  - 定时任务        │      - 分析与监控                   │
└───────────────────┴─────────────────────────────────────┘
          │                        │
          ├────────────────────────┤
          ↓                        ↓
┌─────────────────────────────────────────────────────────┐
│            AI 后端 (FastAPI + LangChain)                │
│  - LangChain 智能体                                      │
│  - MCP 工具集成                                          │
│  - DeepAgents 研究                                       │
│  - LangGraph 工作流                                      │
└─────────────────────────────────────────────────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│          数据库 (PostgreSQL + Drizzle ORM)              │
│  - 用户身份验证                                          │
│  - 对话会话和消息                                        │
│  - 智能体配置                                            │
│  - 执行日志和检查点                                      │
└─────────────────────────────────────────────────────────┘
```

## 🚀 快速开始（全栈）

### 前置要求

- **Node.js**: 18.0 或更高版本
- **Python**: 3.10 或更高版本
- **pnpm**: 8.0 或更高版本
- **PostgreSQL**: 14 或更高版本（或使用 Neon）

### 安装

```bash
# 克隆仓库
git clone https://github.com/AutoAgents-Algorithm-Group/Noma.git
cd Noma

# 安装扩展
cd noma-extension
pnpm install
pnpm dev

# 安装平台
cd ../noma-lp

# 前端
cd frontend
npm install
cp .env.example .env.local
# 配置环境变量
npm run dev

# 后端
cd ../backend
pip install -r requirements.txt
cp .env.example .env
# 配置环境变量
python -m uvicorn src.api.main:app --reload --port 8000
```

### 环境配置

**Noma Extension**（可选后端）:
```env
# backend/.env
OPENAI_API_KEY=your_key
DEEPSEEK_API_KEY=your_key
```

**Noma Platform**:
```env
# frontend/.env.local
DATABASE_URL=postgresql://...
AUTH_SECRET=your_secret
GITHUB_CLIENT_ID=your_client_id
GITHUB_CLIENT_SECRET=your_client_secret
NEXT_PUBLIC_APP_URL=http://localhost:3000

# backend/.env
OPENAI_API_KEY=your_key
TAVILY_API_KEY=your_key
NEXTJS_API_URL=http://localhost:3000
```

## 📚 文档

- **扩展文档**: [noma-extension/README-CN.md](noma-extension/README-CN.md)
- **平台文档**: [noma-lp/README-CN.md](noma-lp/README-CN.md)
- **架构指南**: [noma-lp/docs/](noma-lp/docs/)
- **API 文档**: 后端运行时访问 `http://localhost:8000/docs`

## 🤝 贡献

我们欢迎对两个项目的贡献！请遵循以下指南：

1. **Fork** 仓库
2. **创建**功能分支 (`git checkout -b feature/amazing-feature`)
3. **遵循**各项目的编码风格
4. **彻底测试**您的更改
5. **提交**使用约定式提交 (`feat:`, `fix:`, `docs:` 等)
6. **推送**并打开 Pull Request

### 开发指南

**扩展 (noma-extension)**:
- 使用 React Hooks 的 TypeScript
- Tailwind CSS 样式
- Plasmo 框架约定

**平台 (noma-lp)**:
- 前端: Next.js App Router、TypeScript、Shadcn/UI
- 后端: 带类型提示的 Python、Pydantic 模型
- 数据库: Drizzle ORM 模式定义

## 📄 许可证

本项目采用 MIT 许可证 - 详见 [LICENSE](LICENSE) 文件。

`noma-extension` 和 `noma-lp` 都采用 MIT 许可证。

---

<div align="center">

由 [AutoAgents Algorithm Group](https://github.com/AutoAgents-Algorithm-Group) 用 ❤️ 制作

**如果觉得有用，请给个 Star ⭐！**

</div>
