FROM jellenberger/debian-base

# Switch to root to install packages
USER root

# Install necessary & convenient dependencies
RUN apt-get update && apt-get install -y --no-install-recommends \
         build-essential \
         cmake \
         git \
         curl \
         vim \
         ca-certificates \
         python-qt4 \
         libjpeg-dev \
         zip \
         unzip \
         libpng-dev && \
    apt-get autoremove && apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# Proceed as non-root appuser
USER appuser
WORKDIR $HOME

# Install miniconda
RUN curl -o ~/miniconda.sh -O  https://repo.continuum.io/miniconda/Miniconda3-latest-Linux-x86_64.sh  && \
     chmod +x ~/miniconda.sh && \
     ~/miniconda.sh -b -p $HOME/miniconda3 && \
     rm ~/miniconda.sh && \
    $HOME/miniconda3/bin/conda install conda-build && \
    $HOME/miniconda3/bin/conda update conda && \
    $HOME/miniconda3/bin/conda clean --all
ENV PATH=$PATH:$HOME/miniconda3/bin

# Install Jupyter and some data science packages
RUN conda update conda && \
    conda update -n base conda && \
    conda install -y \
        pip \
        numpy scipy matplotlib pandas jupyter jupyterlab \
        seaborn \
        scikit-learn scikit-image opencv \
        tqdm click \
        sqlalchemy sqlalchemy-utils \
        requests beautifulsoup4 scrapy lxml \
        hdf5 pyarrow && \
    conda install -y -c conda-forge requests-cache && \
    conda clean --all

# Set up working dir
ENV WORKDIR=$HOME/notebooks

# Configure Jupyter
EXPOSE 8888
RUN mkdir $HOME/.jupyter && \
        echo "c.NotebookApp.ip = '*'" > $HOME/.jupyter/jupyter_notebook_config.py && \
        echo "c.NotebookApp.open_browser = False" >> $HOME/.jupyter/jupyter_notebook_config.py && \
        echo "c.NotebookApp.allow_origin = '*'" >> $HOME/.jupyter/jupyter_notebook_config.py && \
        echo "c.NotebookApp.allow_remote_access = False" >> $HOME/.jupyter/jupyter_notebook_config.py

# Switch to working dir and start jupyter
WORKDIR $WORKDIR
CMD ["jupyter", "lab"]
