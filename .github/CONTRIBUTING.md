# Contributing to AutoAgents-Python

Thank you for your interest in contributing to AutoAgents-Python!

We welcome contributions from everyone. This document provides guidelines for contributing to the project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [How to Contribute](#how-to-contribute)
- [Coding Standards](#coding-standards)
- [Commit Guidelines](#commit-guidelines)
- [Pull Request Process](#pull-request-process)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this code.

## Getting Started

1. Fork the repository on GitHub
2. Clone your fork locally
3. Create a new branch for your feature or bug fix
4. Make your changes
5. Push to your fork and submit a pull request

## Development Setup

### Prerequisites

- Python 3.10+
- pip

### Installation

```bash
# Clone repository
git clone https://github.com/yourusername/AutoAgents-Python.git
cd AutoAgents-Python

# Install library in editable mode
cd libs/core  # or agentspro, graph, cua
pip install -e .
```

### Running Tests

```bash
# Run tests for specific library
cd libs/core
pytest

# Run all tests
pytest libs/
```

## How to Contribute

### Reporting Bugs

Before creating bug reports, please check existing issues to avoid duplicates. When creating a bug report, include:

- **Clear title and description**
- **Steps to reproduce** the behavior
- **Expected vs actual behavior**
- **Code snippets** or error messages
- **Environment details**: Python version, OS, library versions

### Suggesting Features

Feature requests are welcome! Please provide:

- **Clear use case**: What problem does it solve?
- **Proposed solution**: How should it work?
- **Alternatives considered**: Other approaches you've thought about
- **Additional context**: Any relevant examples or references

### Pull Requests

1. **Create a feature branch** from `main`:
   ```bash
   git checkout -b feature/amazing-feature
   ```

2. **Make your changes** following our coding standards

3. **Test your changes**:
   ```bash
   pytest
   ```

4. **Commit your changes** with clear messages:
   ```bash
   git commit -m "feat: add amazing feature"
   ```

5. **Push to your fork**:
   ```bash
   git push origin feature/amazing-feature
   ```

6. **Open a Pull Request** with:
   - Clear title and description
   - Reference to related issues
   - Test coverage information

## Coding Standards

### Python

- Follow PEP 8 style guide
- Use type hints for all functions
- Write docstrings for classes and functions
- Use Pydantic for data validation
- Minimum Python version: 3.10

```bash
# Format code with black
black .

# Lint code with ruff
ruff check .

# Type check with mypy
mypy .
```

### Code Style Examples

```python
from typing import Optional
from pydantic import BaseModel

class Agent(BaseModel):
    """AI Agent configuration.
    
    Attributes:
        name: Agent name
        model: LLM model identifier
        temperature: Sampling temperature (0.0-1.0)
    """
    name: str
    model: str
    temperature: float = 0.7
    
    def execute(self, prompt: str) -> Optional[str]:
        """Execute agent with given prompt.
        
        Args:
            prompt: Input prompt string
            
        Returns:
            Agent response or None on error
        """
        pass
```

### General Guidelines

- Write clear, self-documenting code
- Add comments for complex logic
- Keep functions small and focused
- Write tests for new features
- Update documentation as needed

## Commit Guidelines

We follow [Conventional Commits](https://www.conventionalcommits.org/):

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Types

- `feat`: New feature
- `fix`: Bug fix
- `docs`: Documentation changes
- `style`: Code style changes (formatting, no logic change)
- `refactor`: Code refactoring
- `test`: Adding or updating tests
- `chore`: Maintenance tasks

### Scopes

- `core`: Core library changes
- `agentspro`: AgentsPro changes
- `graph`: Graph engine changes
- `cua`: CUA changes

### Examples

```bash
feat(core): add chat streaming support
fix(graph): resolve workflow execution issue
docs(agentspro): update Text2Agent examples
refactor(cua): simplify browser agent initialization
```

## Pull Request Process

1. **Update Documentation**: Ensure README and docs reflect your changes
2. **Update Tests**: Add/update tests for your changes
3. **Check CI**: Ensure all tests pass
4. **Request Review**: Tag maintainers for review
5. **Address Feedback**: Make requested changes
6. **Squash Commits**: Clean up commit history if needed

### PR Checklist

Before submitting, ensure:

- [ ] Code follows project style guidelines
- [ ] Type hints added for new functions
- [ ] Docstrings added for public APIs
- [ ] Tests added/updated and passing
- [ ] Documentation updated
- [ ] No breaking changes (or clearly documented)
- [ ] Related issues linked

## Library-Specific Guidelines

### Core Library

- Focus on stable, well-tested APIs
- Minimize external dependencies
- Ensure backward compatibility

### AgentsPro

- Support multiple workflow formats
- Maintain parser consistency
- Document DSL syntax

### Graph Engine

- Test complex workflow scenarios
- Validate state management
- Document node types

### CUA

- Test on multiple browsers
- Handle edge cases gracefully
- Document automation patterns

## Development Workflow

### Branch Naming

- `feature/` - New features
- `fix/` - Bug fixes
- `docs/` - Documentation
- `refactor/` - Code refactoring
- `test/` - Test updates

### Issue Labels

- `bug` - Something isn't working
- `enhancement` - New feature request
- `documentation` - Documentation improvements
- `good first issue` - Good for newcomers
- `help wanted` - Extra attention needed

## Need Help?

- Check our [documentation](libs/)
- Open an issue with the `question` label
- Join our community discussions

## License

By contributing, you agree that your contributions will be licensed under the [GPL-3.0 License](LICENSE).

---

Thank you for contributing to AutoAgents-Python!

