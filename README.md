# conda-den
Need a central place for various conda environments

## Create Environment

    conda env create -f conda-warp-ide.yml
    conda activate warp-ide
    pip install -r conda-extra-reqs


## Add the environment to Jupyter:

    conda activate warp-ide
    python -m ipykernel install --user --name=warp-ide


## Update the environment

    conda activate warp-ide
    conda env update -f conda-warp-ide.yml --prune


## Combine environments

    conda activate first-env
    conda env update --name first-env --file second.yml
