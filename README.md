# conda-den
Need a place for various conda environments

## Create Environment

    conda env create -f conda-warp-ide.yml
    conda activate warp-ide
    pip install -r conda-extra-reqs

## Update the environment

    conda activate warp-ide
    conda env update -f conda-warp-ide.yml --prune

## Add the environment to Jupyter:

    conda activate warp-ide
    python -m ipykernel install --user --name=warp-ide


## Using virtualenv

Sometimes packages are only available throough pip and since pip and conda
may collide it may be usefull to add a layer of venv before using these
### Create enviroment using  virtualenv
Like python's venv *virtualenv* allows using different python
environments, adding the ability to use existing system packages
without having to install them in the environment as well as
specifying python versions.

To install virtualenv activate the conda environment to use as base

    conda activate warp-ide
    conda install virtualenv

To create an environment (within conda)

    virtualenv --system-site-packages .venv

### Activate virtualenv

On Linux open a shell in the root folder of the repository and run

    source ./.venv/bin/activate
    pip install some-package

On Windows open a command shell in the root folder of the repository and run

    .venv\Scripts\activate
    pip install some-package
