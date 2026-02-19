---
name: uv-priority
description: Prioritize uv over pip for all Python package management and execution. Use when working with ANY Python application (web apps, scripts, data science, ML, dbt, automation, etc.) - installing packages, managing dependencies, or running Python code.
license: MIT
metadata:
  always: true
  emoji: "⚡"
  homepage: https://github.com/marcoracer/uv-priority
  os: [darwin, linux, windows]
  tags: [python, uv, pip, package-management, dbt]
  requires:
    anyBins: [uv]
---

# UV Priority

## CRITICAL: Always Use uv Over pip

This is a **mandatory skill** for all Python-related tasks. When the user mentions installing Python packages, dependencies, or dbt, you **MUST** use `uv` commands instead of `pip`.

## When to Use

Use when:
- Installing ANY Python package or dependency (for ANY Python app: web apps, scripts, data processing, dbt, ML, etc.)
- Setting up Python projects (web apps like Flask/Django/FastAPI, data science, ML, automation, dbt, etc.)
- Installing dependencies for ANY Python-based application
- Creating virtual environments
- Running Python scripts
- Running tests (pytest, unittest, etc.)
- Using dbt commands (dbt-core, dbt-snowflake, etc.)
- ANY task involving Python packages or dependencies

## Command Substitutions (MANDATORY)

NEVER use these pip commands. ALWAYS use the uv equivalent:

| NEVER use pip | ALWAYS use uv |
|---------------|---------------|
| `pip install <package>` | `uv add <package>` |
| `pip install -r requirements.txt` | `uv pip install -r requirements.txt` |
| `pip install dbt-snowflake` | `uv add dbt-snowflake` |
| `pip install dbt-core` | `uv add dbt-core` |
| `pip list` | `uv pip list` |
| `pip freeze` | `uv pip freeze` |
| `python -m venv .venv` | `uv venv` |
| `python script.py` | `uv run script.py` |
| `pytest` | `uv run pytest` |
| `dbt run` | `uv run dbt run` |
| `dbt debug` | `uv run dbt debug` |
| `dbt deps` | `uv run dbt deps` |

## Special Cases for dbt

When installing or working with dbt:
- Install: `uv add dbt-snowflake` (or dbt-postgres, etc.)
- Run dbt commands: `uv run dbt <command>`
- Check dbt version: `uv run dbt --version`

## Priority

`uv` is the **ONLY** option for Python package management. Only consider `pip` as a fallback if:
1. The user explicitly requests `pip`
2. `uv` is not available on the system
3. You receive explicit confirmation from the user
