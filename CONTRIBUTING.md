# Contributing to forked-katoolin

Thank you for your interest in contributing to forked-katoolin! This document provides guidelines and instructions for contributing.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Submitting Changes](#submitting-changes)
- [Adding New Tools](#adding-new-tools)

---

## Code of Conduct

By participating in this project, you agree to maintain a respectful and inclusive environment. Please:

- Be respectful and considerate in all communications
- Welcome newcomers and help them get started
- Focus on constructive feedback
- Accept responsibility for your mistakes and learn from them

---

## Getting Started

### Prerequisites

- Python 2.7+ (Python 3.x preferred for new development)
- Git
- A Linux-based operating system (Ubuntu/Debian recommended for testing)
- Sudo/root access for testing installations

### Repository Structure

```
forked-katoolin/
├── katoolin.py         # Main application (legacy)
├── core/
│   ├── __init__.py
│   ├── categories.py   # Tool categories and package lists
│   └── gear.py         # Core functions and utilities
├── README.md           # Project documentation
├── FEATURES.md         # Proposed features and roadmap
├── CONTRIBUTING.md     # This file
├── LICENCE             # GPL v2 License
└── Changelog.txt       # Version history
```

---

## How to Contribute

### Reporting Bugs

1. Check existing issues to avoid duplicates
2. Open a new issue with the following information:
   - Clear, descriptive title
   - Steps to reproduce the bug
   - Expected behavior
   - Actual behavior
   - System information (OS, Python version)
   - Error messages or logs

### Suggesting Features

1. Check [FEATURES.md](FEATURES.md) for planned features
2. Open an issue with the `feature-request` label
3. Describe the feature and its use case
4. Discuss implementation approach if possible

### Submitting Code

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/your-feature`
3. Make your changes
4. Test your changes thoroughly
5. Commit with clear messages: `git commit -m "Add: description"`
6. Push to your fork: `git push origin feature/your-feature`
7. Open a pull request

---

## Development Setup

### Clone the Repository

```bash
git clone https://github.com/YOUR-USERNAME/forked-katoolin.git
cd forked-katoolin
```

### Create a Virtual Environment (Optional but Recommended)

```bash
python -m venv venv
source venv/bin/activate
```

### Testing Changes

Since katoolin requires root privileges for package installation, use a virtual machine or container for testing:

```bash
# Using Docker for safe testing
docker run -it ubuntu:22.04 /bin/bash

# Inside container
apt update && apt install -y git python3
git clone https://github.com/YOUR-USERNAME/forked-katoolin.git
cd forked-katoolin
python3 core/gear.py  # Test core functionality
```

---

## Coding Standards

### Python Style Guide

- Follow PEP 8 style guidelines
- Use meaningful variable and function names
- Add docstrings to functions and classes
- Keep functions focused and small
- Use type hints where possible (Python 3)

### Example Function Format

```python
def install_tool(tool_name: str, category: str = None) -> bool:
    """
    Install a security tool from the Kali repository.

    Args:
        tool_name: Name of the tool to install
        category: Optional category for logging

    Returns:
        True if installation successful, False otherwise
    """
    # Implementation
    pass
```

### Commit Message Format

Use clear, descriptive commit messages:

```
Type: Brief description

- More detailed explanation if needed
- Reference issues: Fixes #123
```

Types:
- `Add:` New feature or functionality
- `Fix:` Bug fix
- `Update:` Update existing functionality
- `Remove:` Remove code or files
- `Docs:` Documentation changes
- `Refactor:` Code restructuring

---

## Submitting Changes

### Pull Request Process

1. Ensure your code follows the coding standards
2. Update documentation if needed
3. Add or update tests if applicable
4. Ensure all tests pass
5. Update the Changelog.txt if appropriate
6. Submit the pull request with:
   - Clear title and description
   - Reference to related issues
   - Screenshots if UI changes

### Review Process

- Maintainers will review your PR
- Be responsive to feedback
- Make requested changes promptly
- Once approved, your PR will be merged

---

## Adding New Tools

### To add a new security tool to the catalog:

1. Edit `core/categories.py`
2. Add the tool to the appropriate category
3. Verify the package name exists in Kali repositories
4. Test the installation

### Example:

```python
# In core/categories.py
# Add to existing category
4:['web_applications',
    ['apache-users', 'arachni', 'new-tool-name', ...]
]
```

### Verification Steps:

```bash
# Verify package exists
apt-cache search new-tool-name

# Test installation
sudo apt install new-tool-name
```

---

## Questions?

If you have questions about contributing:

1. Check existing issues and documentation
2. Open a discussion issue with the `question` label
3. Be patient and respectful

Thank you for contributing to forked-katoolin!
