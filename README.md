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

The `drafthelper.ipynb` notebook uses `ipywidgets` and `ipydatagrid` for the tabbed hitter/pitcher UI.

If the final `display(tab)` cell runs but no grid appears:

1. Confirm the environment has the widget packages installed:

   ```bash
   pip install -r requirements.txt
   ```

2. Verify Jupyter can see the widget extensions:

   ```bash
   jupyter labextension list
   ```

3. Restart JupyterLab and **restart the notebook kernel**, then run all cells from the top.

4. If output is still blank, trust the notebook and reload it:

   - In JupyterLab: `File` -> `Trust Notebook`
   - Refresh the browser tab and rerun the notebook

`pybaseball` automatically uses its own cache once `cache.enable()` is called in the notebook.

## Next planned notebooks

- Initial draft board and player pool pull
- Position scarcity exploration
- Recent performance window analysis
- Simple model-based ranking experiments
