FROM jellenberger/python-base


USER appuser

RUN export PIP_NO_CACHE_DIR=false && \
    pipenv install numpy scipy matplotlib pandas jupyter notebook

# Set up working dir and configure Jupyter
RUN mkdir $HOME/work && \
    mkdir $HOME/.jupyter && \
    echo "c.NotebookApp.ip = '*'" > $HOME/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.open_browser = False" >> $HOME/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_origin = '*'" >> $HOME/.jupyter/jupyter_notebook_config.py && \
    echo "c.NotebookApp.allow_remote_access = False" >> $HOME/.jupyter/jupyter_notebook_config.py

EXPOSE 8888

CMD ["pipenv", "run", "jupyter", "notebook"]
