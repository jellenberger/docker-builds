## jellenberger/jupyter-base

This is a Docker build for an all-purpose Jupyter notebook environment. It's based on jellenberger/python-base image. It runs Jupyterlab. "Regular" Jupyter is also installed. Typical Conda data science packages are installed, plus a few extras.

Jupyter runs as user `appuser`. Miniconda is installed in `appuser`'s home. `appuser` should be able to use the conda and pip installers without permissions issues.

The included docker-compose file shows the way I like to run the image on Linux. It mounts the current local directory as a working directory inside the container and mounts a local data repository as a data directory inside the container. If your user and group ids are 1000, Linux file permissions should work without hassle. Otherwise, you'll need to specify the correct ids in docker-compose.

A pre-built image can be docker pulled from [jellenberger/jupyter-base](https://cloud.docker.com/repository/docker/jellenberger/jupyter-base).
