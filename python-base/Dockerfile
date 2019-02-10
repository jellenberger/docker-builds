FROM python:3.7-slim-stretch

# Upgrade linux and pip
RUN apt-get update && apt-get -y upgrade && \
    apt-get autoremove && apt-get clean && \
    rm -rf /var/lib/apt/lists/* && \
    python -m pip install --no-cache-dir --upgrade pip

# Create non-root user and user home
ENV HOME=/home/appuser
RUN mkdir -p $HOME && \
    groupadd -g 1000 appuser && \
    useradd -r -u 1000 -g appuser appuser && \
    chown -R appuser:appuser $HOME

# Proceed as non-root user
USER appuser
WORKDIR $HOME

CMD ["bash"]
