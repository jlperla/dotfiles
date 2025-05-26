# Notes on Python Environments
## UV Setup
Time to move away from conda, `uv` 

- Install `uv` automatically or with `curl -LsSf https://astral.sh/uv/install.sh | sh`
- Initialize a new environment and create a new virtual environment, and remove the `main.py` if required.

```bash
uv init
uv venv --python 3.11
```

 - Finally, best to ensure that conda is not in the path variabvles, by checking the `zshrc` files, etc.  If successful, `python` does not work outside of a virtual environment.

## UV File Setup
- Manually go through the requirements files and do an `uv add XXXX` package for them.  These will be added to the pyproject file.  Push the `pyproject.toml` and the `uv.lock` to the repo
- Can use `uv export --format requirements-txt --output requirements.txt` to export to a requirements file, but better to stick with a `.venv`

## Update package versions
```bash
uv pip compile pyproject.toml --upgrade
```

## New Repo Setup
Just use `uv sync` which will create the `.venv` from the pyproject, etc.

# Jupyter with UV
- Will not automatically register kernel with the `uv sync`.
- Can trigger with `python -m ipykernel install --user --name=.venv --display-name "Python (.venv)"`  Only once per project required.

# Scripts
- `uv run` will run the script in the virtual environment, embedded dependencies are in comments in the script.  Use `pixi` for the same format, so no lockin.