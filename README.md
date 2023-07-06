# conda-den
Need a central place for various conda environments

[conda user guide](https://docs.conda.io/projects/conda/en/latest/user-guide/index.html)

[conda cheat sheet](https://docs.conda.io/projects/conda/en/latest/user-guide/cheatsheet.html)

## Create Environment

    conda env create -f conda-jupyter-base.yml
    conda activate jupyter-base
    pip install -r conda-extra-reqs


## Add the environment to Jupyter:

    conda activate jupyter-base
    python -m ipykernel install --user --name=jupyter-base


## Update the environment

    conda activate jupyter-base
    conda env update -f conda-jupyter-base.yml --prune


## Combine environments

    conda activate first-env
    conda env update --name first-env --file second.yml


## Install python kernel

    python -m ipykernel install --user --name=jupyter-base


## Revisions & history

    conda list --revisions
    grep -B1 "^# cmd" ${CONDA_PREFIX}/conda-mhistory 
    

## Channels

    conda config --add channels conda-forge
    conda config --remove channels conda-forge

# Special environments

## Creating an underlying venv for nbdev

    conda activate jupyter-base
    python -m venv --system-site-packages .nbdev
    source .nbdev/bin/activate
    pip install --upgrade pip
    pip install -r pip-nbdev

