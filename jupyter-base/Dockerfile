FROM jupyter/scipy-notebook


USER jovyan

COPY requirements.txt .

RUN pip install --no-cache-dir --user -r requirements.txt

# set up working dir and configure Jupyter
RUN mkdir $HOME/notebooks && \
    mkdir $HOME/.jupyter

COPY jupyter_notebook_config.py $HOME/.jupyter/.

EXPOSE 8888

CMD ["jupyter", "notebook"]
