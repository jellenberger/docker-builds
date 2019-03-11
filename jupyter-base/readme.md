## jellenberger/jupyter-base

This is a simple Docker build for a Jupyter notebook environment. It's based on the jellenberger/python-base image. Jupyter and a handful of data science packages are installed with Pipenv.

Jupyter runs as user `appuser` in a Pipenv environment based at the appuser's home directory. `appuser`'s user and group ids are 1000--if these match the host user's, then file permissions should work fine.

A template docker-compose file is included. It assumes the directory it's run from has a `./work/` directory for notebooks and a `./data/` directory (or symlink) pointing to data.

A pre-built image can be docker pulled from [jellenberger/jupyter-base](https://cloud.docker.com/repository/docker/jellenberger/jupyter-base).
