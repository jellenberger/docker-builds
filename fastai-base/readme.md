## jellenberger/fastai-base

A docker build for an all-purpose fastai v1 notebook environment. Based on the jellenberger/jupyter-base image.

This is a non-GPU image (CUDA is not installed). I use it get data and models organized on a local machine before pushing everything to a GPU-enabled cloud instance for training. It's easier to think when the meter's not running.

The included docker-compose file mounts ./notebooks/ as the working directory for notebooks and ./data as a data directory. If your user and group ids are 1000, Linux file permissions should work for locally-mounted volumes. I like to make ./data a symlink, which seems to work on a Linux host.

Pull built image from Dockerhub at [jellenberger/fastai-base](https://cloud.docker.com/repository/docker/jellenberger/fastai-base).

