## jellenberger/jupyter-base

This is a Docker build for a basic Jupyter notebook environment. It's based on the jellenberger/python-base image.

Jupyter runs as user `appuser` in a Pipenv environment based at the appuser's home directory. `appuser`'s user and group ids are 1000.

The image includes a ~/notebooks directory that is intended to be mounted to a host directory containing notebooks. ~/, not ~/notebooks, is the initial working directory, so that a user has the option of mounting other volumes to be accessed from Jupyter (e.g. a data volume).

An example template docker-compose file is included.

A pre-built image can be docker pulled from [jellenberger/jupyter-base](https://cloud.docker.com/repository/docker/jellenberger/jupyter-base).
