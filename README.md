[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/matchms/notebooks/master?filepath=tutorial.ipynb)

Jupyter notebooks with [matchms](https://github.com/matchms/matchms) tutorial.

Prerequisites

For running locally on Ubuntu:

```shell
sudo apt install jupyter-core
sudo apt install jupyter-notebook
```

Install Miniconda or Anaconda from https://docs.conda.io/projects/conda/en/latest/user-guide/install/linux.html

Create a conda environment:

```shell
conda env create
```
Activate the conda environment:

```shell
conda activate matchms-notebooks
```

While ``matchms`` is being developed, we cannot yet install it from
``conda-forge``, therefore ``matchms`` is not yet listed as a dependency in
``environment.yml``. To circumvent this issue, we will check out a development
copy of ``matchms``, then use ``pip install`` with the ``--editable`` argument
to add it to the ``matchms`` conda environment.

```shell
# (first, change to where you want to store the copy of matchms)
git clone https://github.com/matchms/matchms.git
cd matchms
pip install --editable .
```

Check to see if it all worked by listing the packages that are present in the
conda environment named ``matchms``:

```shell
conda list
```

This should yield a table of packages alongside where they were installed from, like so (excerp):

```shell
libsodium                 1.0.17               h516909a_0    conda-forge
libstdcxx-ng              9.2.0                hdf63c60_2    conda-forge
markupsafe                1.1.1            py38h1e0a361_1    conda-forge
matchms                   0.1.0                     dev_0    <develop>
mistune                   0.8.4           py38h516909a_1000    conda-forge
nb_conda                  2.2.1                    py38_2    conda-forge
nb_conda_kernels          2.2.3                    py38_0    conda-forge
nbconvert                 5.6.1                    py38_0    conda-forge
nbformat                  5.0.4                      py_0    conda-forge
ncurses                   6.1               hf484d3e_1002    conda-forge
notebook                  6.0.3                    py38_0    conda-forge
```

You can tell that ``matchms`` was not retrieved from ``conda-forge`` (the normal
source of packages), but instead was installed from local disk as indicated by
the ``<develop>`` label.

If everything looks OK, start the notebook server:

```shell
jupyter notebook
```

And open a browser to http://localhost:8888 to interact with the notebook.
