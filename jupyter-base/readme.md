## jellenberger/jupyter-base

This is a Docker build for an all-purpose Jupyter notebook environment. It's based on jellenberger/python-base image. It runs Jupyterlab, but "regular" Jupyter is also installed. Typical Conda data science packages are installed, plus a few extras.

Jupyter runs as user `appuser`. Miniconda is installed in `appuser`'s home. `appuser` should be able to use the conda and pip installers without permissions issues.

The included docker-compose file mounts ./notebooks/ as the working directory for notebooks and ./data as a data directory. If your user and group ids are 1000, Linux file permissions should work for locally-mounted volumes. I like to make ./data a symlink, which seems to work on a Linux host.
