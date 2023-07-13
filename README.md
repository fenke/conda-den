# conda-den
Need a central place for various conda environments

[Conda user guide](https://docs.conda.io/projects/conda/en/latest/user-guide/index.html)

[Conda cheat sheet](https://docs.conda.io/projects/conda/en/latest/user-guide/cheatsheet.html)

[Python's venv](https://docs.python.org/3/library/venv.html)


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

    conda activate numdev
    python -m venv --system-site-packages .nbdev
    source .nbdev/bin/activate
    pip install --upgrade pip
    pip install -r pip-nbdev
    python -m ipykernel install --user --name=nbdev

## License infotmation

### Licenses of packages linked in code

[Aiohttp](https://pypi.org/project/aiohttp/) - Apache 2.0
[Asyncpg](https://github.com/MagicStack/asyncpg/blob/master/LICENSE) - Apache 2.0
[Dnspython](https://pypi.org/project/dnspython3/) - Freeware
[Falcon](https://pypi.org/project/falcon/) - Apache 2.0
[Matplotlib](https://pypi.org/project/matplotlib/) - PSF
[Numpy](https://pypi.org/project/numpy/) - BSD
[Pandas](https://pypi.org/project/pandas/) - BSD
[Pip](https://pypi.org/project/pip/) - MIT
[Python](https://docs.python.org/3.10/license.html#psf-license-agreement-for-python-release) - PSF / Python Software Foundation
[Requests](https://pypi.org/project/requests/) Apache 2.0
[Scikit-Learn](https://pypi.org/project/scikit-learn/) - BSD
[SciPy](https://github.com/scipy/scipy/blob/main/LICENSE.txt) - BSD
[Seaborn](https://pypi.org/project/seaborn/) - BSD
[Statsmodels](https://pypi.org/project/statsmodels/) BSD
[PyTorch](https://pypi.org/project/torch/) - BSD
[Uvicorn](https://pypi.org/project/uvicorn/) - BSD
[Xgboost](https://pypi.org/project/xgboost/) - Apache 2.0

### Licenses of development tools

[Hatch](https://pypi.org/project/hatch/) - MIT
[Quarto](https://quarto.org/license.html) - GPL v2 see also [Using programs released under the GNU licenses when writing other programs](https://www.gnu.org/licenses/gpl-faq.en.html#using-programs)
[Jupyter](https://pypi.org/project/jupyter/) - BSD
[jupyter_contrib_nbextensions](https://pypi.org/project/jupyter-contrib-nbextensions/) - BSD
[Jupyterlab](https://pypi.org/project/jupyterlab/) - BSD
[Jupyterlab-git](https://pypi.org/project/jupyterlab-git/) - BSD
[Ipywidgets](https://pypi.org/project/ipywidgets/) - BSD
[Nbdev](https://pypi.org/project/nbdev/) - Apache 2.0
[Spyder](https://pypi.org/project/spyder/) - MIT
[TPOT](https://pypi.org/project/TPOT/) - GPL v2


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
