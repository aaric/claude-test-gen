# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

`claude-test-gen` is a minimal Python project template. Currently, it contains only a basic "Hello World" entry point.

## Environment

- **Python Version**: 3.12+ (specified in [`.python-version`](.python-version))
- **Virtual Environment**: Located at `.venv/`
- **Package Manager**: Uses `pyproject.toml` for project configuration
- **Package Management Tool**: **`uv`** (NOT pip) - Always use `uv` for package management and running services

## Running the Project

```bash
uv run python main.py
```

## Important: Use uv for All Package Operations

**DO NOT use pip** - Always use `uv` for:
- Installing dependencies: `uv pip install <package>` or `uv sync`
- Running scripts: `uv run python <script>.py`
- Adding dependencies: `uv add <package>`
- Virtual environment management

## Project Status

This is a new project with no dependencies, tests, or build configuration yet. The codebase consists of a single entry point file ([`main.py`](main.py)) with minimal functionality.
