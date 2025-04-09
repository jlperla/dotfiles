# Setup Scripts
## Basic Setup
On a new machine, install the following:
1. [VS code](https://code.visualstudio.com/Download) or `brew install --cask visual-studio-code`
2. [Chezmoi](https://www.chezmoi.io): `sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply $GITHUB_USERNAME`

This will automatically install
- oh-my-zsh
- uv

To redo on an existing installation,
```bash
chezmoi init --apply $GITHUB_USERNAME
```

## Optional
- `julia` with `curl -fsSL https://install.julialang.org | sh`