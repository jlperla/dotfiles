# Setup Scripts
## Basic Setup
On a new machine, install the following:
1. [VS code](https://code.visualstudio.com/Download) or `brew install --cask visual-studio-code`
2. [Chezmoi](https://www.chezmoi.io): `sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply $GITHUB_USERNAME`

This will automatically install
- oh-my-zsh
- uv
- ruff

To redo on an existing installation,
```bash
chezmoi init --apply $GITHUB_USERNAME
```

## Adding config file
- `touch ~/.config/ruff/ruff.toml`
- `chezmoi add ~/.config/ruff/ruff.toml`
- `chezmoi edit ~/.config/ruff/ruff.toml`
- `chezmoi apply`

## Local setup:
```bash
mkdir -p ~/.config/chezmoi && chmod 700 ~/.config/chezmoi && cat > ~/.config/chezmoi/chezmoi.local.toml <<'EOF'
[data]
openai_api_key = "sk-REPLACE_ME"
EOF
chmod 600 ~/.config/chezmoi/chezmoi.local.toml
code ~/.config/chezmoi/chezmoi.local.toml
```