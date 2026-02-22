# FantasyBaseballPythonNotebooks

Python and JupyterLab notebooks for drafting and maintaining a fantasy baseball team.

This project is primarily for personal use, but it is organized to be clean, reproducible, and easy for others to run locally.

## What this repo is for

- Pulling MLB data for fantasy baseball workflows (draft prep and in-season management).
- Exploring player performance with basic and intermediate statistics.
- Building lightweight, reusable modeling workflows (including basic sabermetric-style analysis).
- Caching pulled data in Parquet format for fast iteration in notebooks.

## Environment setup (pyenv + virtual environment)

These steps assume `pyenv` is installed on your machine.

1. Install and activate the Python version used by this repo:

   ```bash
   pyenv install -s 3.13.0
   pyenv local 3.13.0
   ```

2. Create and activate a virtual environment:

   ```bash
   python -m venv .venv
   source .venv/bin/activate
   ```

3. Install dependencies:

   ```bash
   pip install --upgrade pip
   pip install -r requirements.txt
   ```

4. Start JupyterLab:

   ```bash
   jupyter lab
   ```

## Core dependencies

- `jupyterlab` for notebook development
- `ipywidgets` for notebook UI controls
- `ipydatagrid` for interactive spreadsheet-like table browsing in notebooks
- `pybaseball` for MLB data collection
- `pandas` for data wrangling
- `pyarrow` for Parquet-based caching/storage

## `drafthelper.ipynb` interactive requirements

The `drafthelper.ipynb` notebook uses `ipywidgets` and `ipydatagrid` for an interactive, spreadsheet-like experience (sorting, scrolling, and editing boolean draft flags directly in the notebook).

For JupyterLab 4, these packages work after a normal `pip install -r requirements.txt` in most environments. If widgets do not render, run this one-time setup command and restart JupyterLab:

```bash
jupyter labextension list
```

If the list output shows disabled or missing widget support, reinstall/upgrade your environment dependencies and relaunch JupyterLab.

## Next planned notebooks

- Initial draft board and player pool pull
- Position scarcity exploration
- Recent performance window analysis
- Simple model-based ranking experiments
