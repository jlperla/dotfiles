# Setup Scripts
## Basic Setup
On a new machine, install the following:
1. [VS code](https://code.visualstudio.com/Download) or `brew install --cask visual-studio-code`
2. [Chezmoi](https://www.chezmoi.io): `sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply $GITHUB_USERNAME`
3. One-time vscode: https://github.com/astral-sh/ruff-vscode?tab=readme-ov-file

This will automatically install
- oh-my-zsh
- uv
- ruff
- julia

To redo on an existing installation,
```bash
chezmoi init --apply $GITHUB_USERNAME
```

## Adding config file
- `touch ~/.config/ruff/ruff.toml`
- `chezmoi add ~/.config/ruff/ruff.toml`
- `chezmoi edit ~/.config/ruff/ruff.toml`
- `chezmoi apply`

## Optional
- `julia` with `curl -fsSL https://install.julialang.org | sh`