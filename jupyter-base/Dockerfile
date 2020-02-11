FROM jupyter/scipy-notebook


USER jovyan

WORKDIR $HOME

COPY --chown=jovyan:users requirements.txt $HOME/

ENV PATH $HOME/.local/bin:$PATH

RUN pip install --no-cache-dir --user -r requirements.txt
