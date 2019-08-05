FROM jellenberger/python-base


USER appuser

COPY requirements.txt .

RUN pip install --no-cache-dir --user -r requirements.txt

# set up working dir and configure Jupyter
RUN mkdir $HOME/notebooks && \
    mkdir $HOME/.jupyter

COPY jupyter_notebook_config.py $HOME/.jupyter/.

EXPOSE 8888

CMD ["jupyter", "notebook"]
