# AutoAgents-Python Monorepo 管理指南

## 📋 概述

本仓库使用 **Git Subtree** 将四个独立的仓库合并成一个 monorepo，同时保留了各自的 Git 历史。

## 🏗️ 仓库结构

```
AutoAgents-Python/                           # 主仓库
├── libs/
│   ├── core/                                # AutoAgents-Core-Python
│   ├── agentspro/                           # AgentsPro-Python
│   ├── graph/                               # AutoAgents-Graph-Python
│   └── cua/                                 # AutoAgents-CUA-Python
```

## 📚 子项目映射

| 子目录 | 原始仓库 |
|--------|---------|
| `libs/core` | [AutoAgents-Core-Python](https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python) |
| `libs/agentspro` | [AgentsPro-Python](https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python) |
| `libs/graph` | [AutoAgents-Graph-Python](https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python) |
| `libs/cua` | [AutoAgents-CUA-Python](https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python) |

## 🔄 从子仓库拉取更新

当原始子仓库有更新时，可以使用以下命令将更新拉取到 monorepo 中：

### 更新 Core 库

```bash
git subtree pull --prefix=libs/core \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python.git \
  main --squash
```

### 更新 AgentsPro 库

```bash
git subtree pull --prefix=libs/agentspro \
  https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python.git \
  main --squash
```

### 更新 Graph 库

```bash
git subtree pull --prefix=libs/graph \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python.git \
  main --squash
```

### 更新 CUA 库

```bash
git subtree pull --prefix=libs/cua \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python.git \
  main --squash
```

## ⬆️ 推送更改到子仓库

如果在 monorepo 中对某个子项目进行了修改，想要推送回原始仓库：

### 推送 Core 库的更改

```bash
git subtree push --prefix=libs/core \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python.git \
  main
```

### 推送 AgentsPro 库的更改

```bash
git subtree push --prefix=libs/agentspro \
  https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python.git \
  main
```

### 推送 Graph 库的更改

```bash
git subtree push --prefix=libs/graph \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python.git \
  main
```

### 推送 CUA 库的更改

```bash
git subtree push --prefix=libs/cua \
  https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python.git \
  main
```

## 💡 最佳实践

### 1. 开发工作流

- **在 monorepo 中开发**：直接在 `libs/*/` 目录中进行开发
- **提交到主仓库**：正常提交到 AutoAgents-Python 主仓库
- **定期同步**：定期将更改推送回各自的子仓库

### 2. 同步策略

**推荐频率**：
- 从子仓库拉取更新：每周或当子仓库有重大更新时
- 推送到子仓库：每个功能完成后或每个 sprint 结束时

**冲突处理**：
- 如果遇到合并冲突，需要手动解决
- 建议使用 `--squash` 选项来保持历史简洁

### 3. 版本管理

每个库应该独立管理版本号：
- 在各自的 `pyproject.toml` 中维护版本
- 发布时同步更新到原始仓库

## 🔧 便捷命令

为了方便操作，可以在 shell 配置文件中添加别名：

```bash
# 添加到 ~/.zshrc 或 ~/.bashrc

# 拉取所有子项目更新
alias pull-all-subtrees='
  git subtree pull --prefix=libs/core https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python.git main --squash &&
  git subtree pull --prefix=libs/agentspro https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python.git main --squash &&
  git subtree pull --prefix=libs/graph https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python.git main --squash &&
  git subtree pull --prefix=libs/cua https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python.git main --squash
'

# 推送特定库
alias push-core='git subtree push --prefix=libs/core https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Core-Python.git main'
alias push-agentspro='git subtree push --prefix=libs/agentspro https://github.com/AutoAgents-Algorithm-Group/AgentsPro-Python.git main'
alias push-graph='git subtree push --prefix=libs/graph https://github.com/AutoAgents-Algorithm-Group/AutoAgents-Graph-Python.git main'
alias push-cua='git subtree push --prefix=libs/cua https://github.com/AutoAgents-Algorithm-Group/AutoAgents-CUA-Python.git main'
```

## 📖 参考资料

- [Git Subtree 官方文档](https://git-scm.com/book/en/v2/Git-Tools-Submodules)
- [Atlassian Git Subtree 教程](https://www.atlassian.com/git/tutorials/git-subtree)

## ❓ 常见问题

### Q: 为什么使用 Subtree 而不是 Submodule？

A: Subtree 的优势：
- 不需要额外的 clone 步骤
- 所有代码都在主仓库中，更容易管理
- 对于不熟悉 monorepo 的开发者更友好

### Q: 如何查看某个子项目的历史？

```bash
git log --oneline -- libs/core/
```

### Q: 推送到子仓库失败怎么办？

1. 检查是否有推送权限
2. 确保子仓库的分支存在
3. 尝试先从子仓库拉取最新更改，再推送

---

<div align="center">

**有问题？欢迎提交 Issue！**

</div>

