<!--
Fields:
 - COMMAND - the command to run the project
 - PROJECT_NAME
 - GITHUB_ACCOUNT
 

-->

# [Project Name]

[![uv](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/uv/main/assets/badge/v0.json)](https://github.com/astral-sh/uv)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://github.com/astral-sh/ruff)

## Project Description

## Usage Examples

## Installation

This project uses uv for development, and uv is also the easiest way to run the project.

> uv docs:  
>[Astral - uv](https://docs.astral.sh/uv/)  
>[https://docs.astral.sh/uv/concepts/tools/](https://docs.astral.sh/uv/concepts/tools/)  
>[https://docs.astral.sh/uv/reference/cli/#uv-tool](https://docs.astral.sh/uv/reference/cli/#uv-tool)  
>[https://docs.astral.sh/uv/pip/packages/#installing-a-package](https://docs.astral.sh/uv/pip/packages/#installing-a-package)  
>[https://docs.astral.sh/uv/concepts/projects/dependencies/#dependency-sources](https://docs.astral.sh/uv/concepts/projects/dependencies/#dependency-sources)

To run with uv:  
>Note the url format for tool install is the same as that for uv pip install:  

```bash
# run esi-auth without installing
uvx --from git+https://github.com/GITHUB_ACCOUNT/PROJECT_NAME@main PROJECT_NAME

# OR

# Install to Path
uv tool install --from git+https://github.com/GITHUB_ACCOUNT/PROJECT_NAME@main PROJECT_NAME
# and run
COMMAND ARGS
```

## Development

### Download the source code:

```bash
git clone https://github.com/GITHUB_ACCOUNT/PROJECT_NAME.git
cd PROJECT_NAME
uv sync
# activate the venv if desired
source ./.venv/bin/activate
```

### Use as a dependency in another project:

```toml
# in your pyproject.toml file, for a uv managed project
dependencies = ["PROJECT_NAME"]
[tool.uv.sources]
PROJECT_NAME = { git = "https://github.com/GITHUB_ACCOUNT/PROJECT_NAME", branch = "main" }
```

### ruff settings for formatting and linting

```toml
[tool.ruff.lint]
select = ["B", "UP", "D", "DOC", "FIX", "I", "F401"]
# non-imperative-mood (D401)
ignore = ["D401", "D101"]
# extend-select = ["I"]

[tool.ruff.lint.pydocstyle]
convention = "google"

[tool.ruff.format]
docstring-code-format = true
docstring-code-line-length = 88
```

## Contributing