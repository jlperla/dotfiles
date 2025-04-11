# Notes on Python Environments
## UV Setup
Time to move away from conda, `uv` 

- Install `uv` automatically or with `curl -LsSf https://astral.sh/uv/install.sh | sh`
- Initialize a new environment and create a new virtual environment, and remove the `main.py` if required.

```bash
uv init
uv venv --python 3.11
```
- Can set the python interpreter for the project, or just rely on setting the default in vscode config:
```json
{
"python.defaultInterpreterPath": "./.venv/bin/python"
}
```
 - Finally, best to ensure that conda is not in the path variabvles, by checking the `zshrc` files, etc.  If successful, `python` does not work outside of a virtual environment.

## UV File Setup
- Manually go through the requirements files and do an `uv add XXXX` package for them.  These will be added to the pyproject file.  Push the `pyproject.toml` and the `uv.lock` to the repo
- Can use `uv export --format requirements-txt --output requirements.txt` to export to a requirements file, but better to stick with a `.venv`

## New Repo Setup
Just use `uv sync` which will create the `.venv` from the pyproject, etc.
