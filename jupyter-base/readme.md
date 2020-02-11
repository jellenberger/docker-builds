## jellenberger/jupyter-base

These are Docker build & compose templates for a Jupyter notebook environment. They blithely ignore any potential user permission issues by assuming the current user has UID 1000 and the relevant local directories have already been created.

`docker-compose.yml` simply runs a [jupyter/scipy-notebook](https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook), mapping the current directory's `./work` and `./data` subdirectories to `/home/jovyan`.

`docker-compose-custom.yml` works similarly, but builds and runs a [jupyter/scipy-notebook](https://github.com/jupyter/docker-stacks/tree/master/scipy-notebook)-based image (see `Dockerfile`) with additional libraries from `requirements.txt` installed. The additional libraries are installed at the user level with pip: simpler and faster than a conda install but could possibly cause breakage.
