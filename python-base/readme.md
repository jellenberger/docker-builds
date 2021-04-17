# jellenberger/python-base

This is template Dockerfile to build a Python environment from a slim Python 3 image.

It includes: 

- wait-for-it utility script (See https://docs.docker.com/compose/startup-order/)

- a non-root user: `appuser`, UID & GID 1000

- Pipenv installed at system level

- Pipenv dependencies installed from local Pipfile and Pipfile.lock

- local code copied to `~/code`
