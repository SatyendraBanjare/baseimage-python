FROM python:3
ARG SSH_KEY
USER root

########################
# Install basics
########################
RUN apt-get update && apt-get install --no-install-recommends -y \
    sudo \
    neovim \
    tmux \
    ncdu \
    htop \
    zsh
########################

########################
# Setup Git & clone repo
########################
RUN mkdir -p /root/.ssh/ && \
    echo "$SSH_KEY" > /root/.ssh/id_rsa && \
    chmod -R 600 /root/.ssh/ && \
    ssh-keyscan -t rsa github.com >> ~/.ssh/known_hosts

RUN git config --global user.name "Satyendra Kumar Banjare"
RUN git config --global user.email "satyendrabanjare99@gmail.com"

RUN mkdir /workdir
RUN git clone git@github.com:SatyendraBanjare/baseimage-python.git /workdir/baseimage-python
########################

WORKDIR /workdir
