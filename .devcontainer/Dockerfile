FROM python:3

ARG SSH_KEY

RUN pip install --no-cache-dir --upgrade pip 

RUN mkdir -p /root/.ssh/ && \
    echo "$SSH_KEY" > /root/.ssh/id_rsa && \
    chmod -R 600 /root/.ssh/ && \
    ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts

RUN mkdir /workdir
RUN git clone git@github.com:SatyendraBanjare/baseimage-python.git /workdir/baseimage-python

WORKDIR /workdir
