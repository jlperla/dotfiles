# Some VS Code Settings
- One-time vscode for [ruff](https://github.com/astral-sh/ruff-vscode?tab=readme-ov-file)
- Can set the python interpreter for the project, or just rely on setting the default in vscode config:
```json
{
"python.defaultInterpreterPath": "./.venv/bin/python"
}
```
Even better, in a `.zshrc`:
```
# Activate virtualenv if interactive shell and in a project directory
if [[ $- == *i* ]]; then
  [ -f ".venv/bin/activate" ] && source .venv/bin/activate 2>/dev/null
fi
```