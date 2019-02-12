## jellenberger/fastai-base

A docker build for an all-purpose fastai v1 notebook environment. Based on the jellenberger/jupyter-base image.

This is a non-GPU image (CUDA is not installed). I use it get data and models organized on a local machine before pushing everything to a GPU-enabled cloud instance for training. It's easier to think when the meter's not running.

The included docker-compose file shows the way I like to run the image on Linux. It mounts the current local directory as a working directory inside the container and mounts a local data repository as a data directory inside the container. If your user and group ids are 1000, Linux file permissions should work without hassle. Otherwise, you'll need to specify the correct ids in docker-compose.

Pull built image can be docker pulled from [jellenberger/fastai-base](https://cloud.docker.com/repository/docker/jellenberger/fastai-base).
