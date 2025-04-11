# Setup Scripts
## Basic Setup
On a new machine, install the following:
1. [VS code](https://code.visualstudio.com/Download) or `brew install --cask visual-studio-code`
2. [Chezmoi](https://www.chezmoi.io): `sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply $GITHUB_USERNAME`

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

## Add to Keychain
```bash
chezmoi secret keyring set --service=openai --user=jlperla
```
Save the value, then in the `.zshrc` file, add:
```bash
export OPENAI_API_KEY="{{ keyring "openai" "jlperla" }}"
```