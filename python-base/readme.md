# jellenberger/python-base

This is a Docker build for a simple Python 3 image. It is essentially a Python 3 Debian slim image with a non-root user and [Pipenv](https://pipenv.readthedocs.io/en/latest/) added.

The user, `appuser`, has a home directory at `\home\appuser`. `appuser` has a user and primary group ids of 1000.

The image starts a bash shell instead of Python

Pull a built image from Dockerhub at [jellenberger/python-base](https://cloud.docker.com/repository/docker/jellenberger/python-base).
