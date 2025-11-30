<div align="center">

<img src="https://img.shields.io/badge/-Noma-000000?style=for-the-badge&labelColor=faf9f6&color=faf9f6&logoColor=000000" alt="Noma" width="320"/>

<h4>AI Agent Platform Ecosystem</h4>

**English** | [简体中文](README-CN.md)

<a href="https://github.com/AutoAgents-Algorithm-Group/Noma">
  <img alt="GitHub version" src="https://img.shields.io/badge/version-0.0.1-blue.svg?style=for-the-badge" />
</a>
<a href="LICENSE">
  <img alt="License MIT" src="https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge" />
</a>

</div>

Noma is a comprehensive AI agent platform ecosystem consisting of a **browser extension** for web automation and a **landing page/platform** for user management and agent orchestration.

## 📦 Monorepo Structure

This repository contains two main projects:

```
Noma/
├── noma-extension/          # 🌐 Browser Extension (Chrome/Edge)
│   ├── src/                 # Extension source code
│   ├── backend/             # Optional Python backend for AI
│   └── README.md            # Extension documentation
│
├── noma-lp/                 # 🚀 Landing Page & Platform
│   ├── frontend/            # Next.js web application
│   ├── backend/             # FastAPI backend
│   ├── docker/              # Docker deployment
│   └── README.md            # Platform documentation
│
├── .gitignore              # Unified gitignore
├── LICENSE                 # MIT License
└── README.md               # This file
```

## 🌐 Noma Extension

**Web-Native AI Agent Platform for Browser Automation**

A Chrome/Edge extension that enables creating and running AI agents directly in your browser for automating web tasks.

### Key Features
- 🤖 **Action Recorder**: Record web interactions and convert to automation
- 🔧 **Agent Builder**: Visual workflow editor for complex automation
- 💬 **AI Chat Assistant**: Control browser with natural language
- ⏰ **Scheduled Tasks**: Run agents automatically on schedule

### Quick Start

```bash
cd noma-extension
pnpm install
pnpm dev
# Load build/chrome-mv3-dev/ in Chrome
```

📖 **Full Documentation**: [noma-extension/README.md](noma-extension/README.md)

## 🚀 Noma Platform (Landing Page)

**Full-Stack AI Agent Management Platform**

A comprehensive web platform for managing users, agents, and orchestrating multi-agent workflows.

### Key Features
- 🔐 **Authentication**: Better Auth with GitHub OAuth
- 💬 **Agent Chat**: Real-time streaming chat with AI agents
- 🔧 **MCP Integration**: Model Context Protocol for tool management
- 📊 **Deep Research**: Multi-agent research workflows

### Tech Stack
- **Frontend**: Next.js 16 + TypeScript + Shadcn/UI
- **Backend**: FastAPI + LangChain + LangGraph
- **Database**: PostgreSQL (Neon) + Drizzle ORM
- **Auth**: Better Auth

### Quick Start

```bash
cd noma-lp

# Frontend
cd frontend
npm install
npm run dev  # Runs on http://localhost:3000

# Backend
cd ../backend
pip install -r requirements.txt
python -m uvicorn src.api.main:app --reload --port 8000
```

📖 **Full Documentation**: [noma-lp/README.md](noma-lp/README.md)

## 🏗️ Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                    User Interface                       │
├───────────────────┬─────────────────────────────────────┤
│  Browser Extension │      Web Platform (Next.js)        │
│  (Noma Extension) │      (Noma Landing Page)           │
│  - Record actions │      - User management             │
│  - Build workflows│      - Agent orchestration         │
│  - Execute agents │      - Team collaboration          │
│  - Schedule tasks │      - Analytics & monitoring      │
└───────────────────┴─────────────────────────────────────┘
          │                        │
          ├────────────────────────┤
          ↓                        ↓
┌─────────────────────────────────────────────────────────┐
│              AI Backend (FastAPI + LangChain)           │
│  - LangChain Agents                                     │
│  - MCP Tool Integration                                 │
│  - DeepAgents Research                                  │
│  - LangGraph Workflows                                  │
└─────────────────────────────────────────────────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│           Database (PostgreSQL + Drizzle ORM)           │
│  - User authentication                                  │
│  - Chat sessions & messages                             │
│  - Agent configurations                                 │
│  - Execution logs & checkpoints                         │
└─────────────────────────────────────────────────────────┘
```

## 🚀 Quick Start (Full Stack)

### Prerequisites

- **Node.js**: 18.0 or higher
- **Python**: 3.10 or higher
- **pnpm**: 8.0 or higher
- **PostgreSQL**: 14 or higher (or use Neon)

### Installation

```bash
# Clone repository
git clone https://github.com/AutoAgents-Algorithm-Group/Noma.git
cd Noma

# Install Extension
cd noma-extension
pnpm install
pnpm dev

# Install Platform
cd ../noma-lp

# Frontend
cd frontend
npm install
cp .env.example .env.local
# Configure environment variables
npm run dev

# Backend
cd ../backend
pip install -r requirements.txt
cp .env.example .env
# Configure environment variables
python -m uvicorn src.api.main:app --reload --port 8000
```

### Environment Setup

**Noma Extension** (Optional Backend):
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

## 📚 Documentation

- **Extension Documentation**: [noma-extension/README.md](noma-extension/README.md)
- **Platform Documentation**: [noma-lp/README.md](noma-lp/README.md)
- **Architecture Guide**: [noma-lp/docs/](noma-lp/docs/)
- **API Documentation**: Available at `http://localhost:8000/docs` when backend is running

## 🤝 Contributing

We welcome contributions to both projects! Please follow these guidelines:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/amazing-feature`)
3. **Follow** the coding style of each project
4. **Test** your changes thoroughly
5. **Commit** with conventional commits (`feat:`, `fix:`, `docs:`, etc.)
6. **Push** and open a Pull Request

### Development Guidelines

**Extension (noma-extension)**:
- TypeScript with React hooks
- Tailwind CSS for styling
- Plasmo framework conventions

**Platform (noma-lp)**:
- Frontend: Next.js App Router, TypeScript, Shadcn/UI
- Backend: Python with type hints, Pydantic models
- Database: Drizzle ORM schema definitions

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

Both `noma-extension` and `noma-lp` are licensed under MIT.

---

<div align="center">

Made with ❤️ by [AutoAgents Algorithm Group](https://github.com/AutoAgents-Algorithm-Group)

**Star ⭐ this repo if you find it useful!**

</div>
