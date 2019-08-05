# jellenberger/python-base

This is a Docker build for a simple Python 3 image: a Python 3 Debian slim image with a non-root user added.

The user, `appuser`, has a home directory at `\home\appuser`. `appuser` has user and primary group ids of 1000.

The image starts a bash shell instead of Python

On Dockerhub at [jellenberger/python-base](https://cloud.docker.com/repository/docker/jellenberger/python-base).
