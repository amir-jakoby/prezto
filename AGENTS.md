# Repository Guidelines

## Project Structure & Module Organization
- `modules/` contains Prezto modules (each module in its own folder with `alias.zsh`, `init.zsh`, or `README.md`). Example: `modules/git/alias.zsh`.
- `runcoms/` holds the user-facing Zsh runcom templates (linked into `$ZDOTDIR` as `.zshrc`, `.zprofile`, etc.).
- `init.zsh` is the entry point that wires modules and runcoms together.
- `contrib/` contains optional third‑party modules.

## Build, Test, and Development Commands
- No build system or test suite is defined here.
- Common maintenance commands (from README):
  - `zprezto-update` checks for updates and pulls submodules.
  - `git submodule update --init --recursive` refreshes external modules.

## Coding Style & Naming Conventions
- Zsh scripts use 2‑space indentation and align line continuations with `\`.
- Keep files focused: aliases in `alias.zsh`, module setup in `init.zsh`.
- Prefer lowercase, descriptive names for aliases and zstyles; follow existing module naming patterns (e.g., `:prezto:module:<name>:...`).

## Testing Guidelines
- No automated tests are provided. Validate changes manually:
  - reload Zsh or run `source ~/.zshrc`
  - verify module behavior and prompt rendering

## Commit & Pull Request Guidelines
- Commit style in history often uses a module prefix: `module: short description` (e.g., `prompt: update ...`). Keep subjects concise and lowercase.
- If updating submodules, include the new submodule version in the message.
- PRs should describe the user-visible behavior change, affected modules, and any manual verification steps.

## Configuration & Safety Tips
- Changes may affect shell startup; keep edits minimal and backward‑compatible.
- When touching runcoms, note the expected symlink targets in `$ZDOTDIR`.
- For new modules, add a brief `README.md` under the module directory explaining usage.
