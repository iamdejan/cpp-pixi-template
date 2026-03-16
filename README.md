# C++ Pixi Template

This is a simple repository template for C++ projects. C++ is compiled with clang++, managed by Pixi.

## Prerequisites

Before running this program, ensure you have the following installed:

1. **Pixi** - A package manager for Rust and other languages. Install it by following the official guide at [https://pixi.prefix.dev/latest/](https://pixi.prefix.dev/latest/).

2. **Download Dependencies** - Once Pixi is installed, run the following command to download all project dependencies:
   ```bash
   pixi install
   ```

3. **Build the project** - If you want to build the project without running it, run the following command:
   ```bash
   pixi run build
   ```

## Run the Program

Use the following command to build and run the project:
   ```bash
   pixi run start
   ```

## Project Tree Structure

```
Root/
├── pixi.toml               # Pixi workspace configuration
├── pixi.lock               # Pixi lockfile
├── .gitignore              # Git ignore rules
├── .gitattributes          # Git attributes
├── .editorconfig           # Editor configuration
├── .clang-format           # Clang-Format code style configuration
├── AGENTS.md               # Agent rules and guidelines
├── .github/                # GitHub workflows
│   └── workflows/
│       ├── pr-pipeline.yaml
│       └── trunk-pipeline.yaml
├── src/
│   └── main.cpp            # Main entry point
└── README.md               # Project documentation
```

This section explains the purpose of each file in the repository:

### Root Directory Files

| File | Description |
|------|-------------|
| [`pixi.toml`](pixi.toml) | Pixi workspace configuration that defines the project name, authors, platforms, available tasks (build, start, fmt, lint), and dependencies (clangxx, clang-tidy, clang-format). |
| [`pixi.lock`](pixi.lock) | Lockfile for Pixi that pins the exact versions of all dependencies. This file should be committed to ensure reproducible environments. |
| [`.gitignore`](.gitignore) | Specifies files and directories that Git should ignore (e.g., build artifacts, IDE files, pixi environments in `.pixi/`). |
| [`.gitattributes`](.gitattributes) | Git configuration that sets `pixi.lock` to use binary merging (to avoid merge conflicts) and marks it as YAML-generated. |
| [`.editorconfig`](.editorconfig) | Editor configuration that ensures consistent coding style across different editors (e.g., 4-space indentation for C++ files). |
| [`.clang-format`](.clang-format) | Clang-Format configuration that defines the code style rules for formatting C++ code. |
| [`AGENTS.md`](AGENTS.md) | Rules and guidelines for the Kilo Code assistant, including code generation and debugging procedures. |

### Source Files

| File | Description |
|------|-------------|
| [`src/main.cpp`](src/main.cpp) | The main entry point of the C++ application. Currently contains a simple "Hello, world!" program. |

### Configuration Directories

| Path | Description |
|------|-------------|
| [`.github/`](.github/) | GitHub Actions workflows for CI/CD pipelines. Contains `pr-pipeline.yaml` for pull request checks and `trunk-pipeline.yaml` for the main branch pipeline. |
