# Jupyter Kernels & Environments — Ready to copy/paste

Commands shown one per block for easy copy/paste. A brief description follows each command.

## Create & activate environments

```sh
python -m venv .venv
```
Create a lightweight virtualenv named .venv.

```sh
source .venv/bin/activate
```
Activate the virtualenv on Linux/macOS (use .venv\Scripts\activate on Windows).

```sh
conda create -n myenv python=3.10 -y
```
Create a conda environment named myenv.

```sh
conda activate myenv
```
Activate the conda environment.

```sh
pipenv install --python 3.10
```
Create a Pipenv environment and install Python.

```sh
poetry init --no-interaction && poetry add python@3.10
```
Create a Poetry project and set Python (example usage).

## Install kernel support in the env

```sh
pip install ipykernel
```
Install the IPython kernel package into the active environment.

```sh
conda install -c conda-forge ipykernel -y
```
Install ipykernel via conda.

## Register environment as a Jupyter kernel

```sh
python -m ipykernel install --user --name myenv --display-name "Python (myenv)"
```
Register the active env as a kernel named myenv with a friendly display name.

```sh
python -m ipykernel install --name myenv --user --display-name "Python (myenv) - v3.10"
```
Register a kernel with a custom display name including version info.

```sh
poetry run python -m ipykernel install --user --name poetry-env --display-name "Python (poetry)"
```
Register a Poetry-managed environment as a kernel.

## List, inspect, and remove kernels

```sh
jupyter kernelspec list
```
List all installed Jupyter kernels and their filesystem locations.

```sh
jupyter kernelspec uninstall myenv -f
```
Uninstall the kernel named myenv (force with -f).

```sh
ls $(jupyter --data-dir)/kernels
```
Show kernel directories in Jupyter's data path.

## Start and manage Jupyter servers

```sh
jupyter notebook
```
Start the classic Jupyter Notebook server.

```sh
jupyter lab
```
Start JupyterLab.

```sh
jupyter notebook --no-browser --port=8888
```
Start notebook headless on port 8888 (useful on remote machines).

```sh
jupyter notebook list
```
Show running Jupyter server instances and their tokens/ports.

```sh
jupyter notebook stop 8888
```
Stop the Jupyter server listening on port 8888.

## Convert and run notebooks from CLI

```sh
jupyter nbconvert --to html notebook.ipynb
```
Convert notebook to HTML.

```sh
jupyter nbconvert --to notebook --execute notebook.ipynb --inplace
```
Execute a notebook and overwrite it with output.

## Troubleshooting & kernel control

```sh
jupyter kernelspec list --json
```
Output kernelspec details as JSON (useful for automation).

```sh
ps aux | grep -E "jupyter|ipykernel" | grep -v grep
```
Find running Jupyter and kernel processes (kill if necessary).

```sh
pkill -f ipykernel
```
Terminate ipykernel processes (use carefully).

```sh
python -m pip install --upgrade ipykernel
```
Upgrade ipykernel in the environment to fix compatibility issues.

## Using kernels in editors & CI

```sh
# VS Code: ensure env is activated, then install kernel:
python -m ipykernel install --user --name vscode-env --display-name "Python (vscode-env)"
```
Make the environment available as a kernel in VS Code notebooks.

```sh
# CI: run a notebook using nbconvert in a virtualenv
source .venv/bin/activate && pip install -r requirements.txt && jupyter nbconvert --to notebook --execute ci_notebook.ipynb --ExecutePreprocessor.timeout=600
```
Example CI command: activate env, install deps, and execute a notebook.

## Quick tips
- After creating/updating an env, reinstall the ipykernel to refresh the kernel display and python path.
- Use descriptive --display-name so you can easily pick the correct kernel in notebook UI.
- Keep heavy dependencies out of kernels you share (use dedicated envs for experiments).