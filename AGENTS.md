# AGENTS.md

## Code Generation

Make sure you adhere to the guide on this file to generate the code.

### Rules of engagement

1. You're allowed to create functions, structs and impl blocks to generate the code.
2. With the exception of import statements and Cargo macros (allow and deny), explain the flow of the program using comments. Make sure that you write not only what the program is doing, but why. It will help me to judge your work.
3. You have to add C++ documentation. The documentation should contain what is the function for (basically the description), a brief summary of the steps, and input and output parameters. If your function has the ability to throw panic, please state it in the documentation as well.

### Debugging

In this repository, we don't have `clang++`, `clang-tidy`, and `clang-format` installed in local machine. Instead, those commands are managed by Pixi, which is why in [pixi.toml](pixi.toml) under `[dependencies]` section you will have `clangxx`, `clang-tidy`, and `clang-format` listed as dependencies.

The consequence is that every `clang++`, `clang-tidy`, and `clang-format` command you want to run should be run under `pixi run` command. I will list some of the examples here:
- Check Rust version: Instead of `clang++ --version`, you should run `pixi run clang++ --version`.
- Build the program: Instead of `clang++ ...`, you should run `pixi run clang++ ...` (`...` here simply means the extra arguments).
  - For building the program, run `pixi run build` instead, as defined in [pixi.toml](pixi.toml).
- List down all checks used for lint: Instead of `clang-tidy -checks='*' -list-checks`, you should run `pixi run clang-tidy -checks='*' -list-checks`.

## Code Validation

After generating the code, make sure you validate the code you generated.

### Steps to Validate

Run these commands in sequence:
1. `pixi run fmt`: format your code. This ensures that the code written by human and by you (coding agent) are consistent, following the style that Rust has provided.
2. `pixi run lint`: ensure no linter errors.
3. `pixi run start`: run the code.

## Update Documentation

After the validation is finished, update the project tree structure and file descriptions in README.md if needed. This is to ensure we always have updated documentation.

### Available Commands

| Command | Description |
|---------|-------------|
| `pixi run build` | Build the Rust project |
| `pixi run start` | Build and run the program |
| `pixi run fmt` | Format the code using rustfmt |
| `pixi run lint` | Run clippy linter (includes fmt check) |
