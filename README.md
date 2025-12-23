<div align="center">

<img src="https://img.shields.io/badge/-AutoAgents Python-000000?style=for-the-badge&labelColor=faf9f6&color=faf9f6&logoColor=000000" alt="AutoAgents" width="320"/>

<h4>Python AI Agent Framework - Monorepo</h4>

<a href="LICENSE">
  <img alt="License MIT" src="https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge" />
</a>

</div>

**AutoAgents-Python** is a comprehensive Python-based AI agent framework ecosystem, consisting of four modular libraries that work together to provide powerful AI agent capabilities.

## Monorepo Structure

This repository contains four main libraries:

```
AutoAgents-Python/
├── libs/
│   ├── core/                # Core Library - Chat, Knowledge Base, Data Science, etc.
│   │   ├── src/             # Core implementations
│   │   ├── playground/      # Example scripts and tests
│   │   ├── pyproject.toml   # Package configuration
│   │   └── README.md        # Core documentation
│   │
│   ├── agentspro/           # AgentsPro - Text-to-Agent conversion
│   │   ├── src/             # AgentsPro implementations
│   │   ├── pyproject.toml   # Package configuration
│   │   └── README.md        # AgentsPro documentation
│   │
│   ├── graph/               # Graph Engine - Agent workflow orchestration
│   │   ├── src/             # Graph engine implementations
│   │   ├── playground/      # Example workflows
│   │   ├── pyproject.toml   # Package configuration
│   │   └── README.md        # Graph documentation
│   │
│   └── cua/                 # Computer Use Agent - Browser & UI automation
│       ├── src/             # CUA implementations
│       ├── playground/      # Example automations
│       ├── pyproject.toml   # Package configuration
│       └── README.md        # CUA documentation
│
├── .gitignore              # Unified gitignore
├── LICENSE                 # MIT License
└── README.md               # This file
```

## Core Library

**Foundational AI Agent Capabilities**

The core library provides essential functionalities for building AI agents:

- **Chat Client**: Multi-model LLM chat interface
- **Knowledge Base**: Vector database for RAG applications
- **Crawl Client**: Web scraping and data extraction
- **MCP Integration**: Model Context Protocol support
- **Data Science Agent**: Automated data analysis and visualization
- **Slide Generation**: PPT creation and manipulation

**Documentation**: [libs/core/README.md](libs/core/README.md)

## AgentsPro

**Text-to-Agent Conversion Framework**

AgentsPro enables converting natural language descriptions into executable agent workflows:

- Text-to-workflow conversion
- Integration with Dify and Agentify
- Flow graph interpretation

**Documentation**: [libs/agentspro/README.md](libs/agentspro/README.md)

## Graph Engine

**Agent Workflow Orchestration**

The graph engine provides powerful workflow orchestration for complex multi-agent systems:

- State-based workflow execution
- Parallel and conditional branching
- Loop and iteration support
- Visual workflow design
- Integration with Dify and Agentify formats

**Documentation**: [libs/graph/README.md](libs/graph/README.md)

## Computer Use Agent (CUA)

**Browser & UI Automation Framework**

CUA provides comprehensive browser automation and computer control capabilities:

- **Browser Agent**: Web automation with AI
- **Computer Agent**: Desktop application control
- **Mobile Agent**: Mobile app automation
- **Captcha Solver**: Automated captcha solving
- **Pre-built Agents**: Login, search, and more

**Documentation**: [libs/cua/README.md](libs/cua/README.md)

## Quick Start

### Prerequisites

- **Python**: 3.10 or higher
- **pip**: Latest version

### Installation

Each library can be installed independently:

```bash
# Install Core Library
cd libs/core
pip install -e .

# Install AgentsPro
cd ../agentspro
pip install -e .

# Install Graph Engine
cd ../graph
pip install -e .

# Install CUA
cd ../cua
pip install -e .
```

### Basic Usage

**Core Library - Chat Example**:
```python
from autoagents_core.client import ChatClient

client = ChatClient(api_url="YOUR_API_URL", api_key="YOUR_API_KEY")
response = client.send_message("Hello, AI!")
print(response)
```

**Graph Engine - Workflow Example**:
```python
from autoagents_graph.engine import GraphEngine

engine = GraphEngine()
workflow = engine.load_workflow("path/to/workflow.yaml")
result = await engine.execute(workflow, inputs={"query": "test"})
```

**CUA - Browser Automation Example**:
```python
from autoagents_cua.agent import BrowserAgent

agent = BrowserAgent()
await agent.navigate("https://example.com")
await agent.click("button[type='submit']")
```

## Architecture Overview

```
┌─────────────────────────────────────────────────────────┐
│                    Application Layer                    │
│  - Custom AI Agents                                     │
│  - Business Logic                                       │
└─────────────────────────────────────────────────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│                  AutoAgents Libraries                   │
├─────────────┬──────────────┬──────────────┬────────────┤
│    Core     │  AgentsPro   │    Graph     │    CUA     │
│  (Clients)  │ (Text2Agent) │  (Workflow)  │ (Browser)  │
└─────────────┴──────────────┴──────────────┴────────────┘
          │
          ↓
┌─────────────────────────────────────────────────────────┐
│              External Services & APIs                   │
│  - LLM Providers (OpenAI, Anthropic, etc.)             │
│  - Vector Databases (Supabase, etc.)                   │
│  - Browser Engines (Playwright, Selenium)              │
└─────────────────────────────────────────────────────────┘
```
