## Build file for my personal general-purpose cpu version of fastai v1.
## I use it for setting up data and models on a local machine before pushing
## the notebooks up to a cloud GPU instance.

FROM jellenberger/jupyter-base

# Ensure we're working as non-root user appuser 
USER appuser

# Install fastai
RUN conda update conda && \
    conda install -y -c pytorch -c fastai fastai && \
    conda clean --all

# Ensure we're in the correct working environment
ENV WORKDIR=$HOME/work
WORKDIR $WORKDIR

CMD ["jupyter", "lab"]
