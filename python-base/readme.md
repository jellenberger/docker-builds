# jellenberger/python-base

This is template Dockerfile to build a dev environment from a slim Python 3 image.

It includes: 

- wait-for-it utility script (See https://docs.docker.com/compose/startup-order/)

- a non-root user to run code (`appuser`, UID & GID 1000) with home `/home/appuser`

- Pipenv installed at system level (no need to activate an environment)

- Pipenv dependencies (including dev) installed from the local Pipfile and Pipfile.lock

- local code copied to `/home/appuser/work`
