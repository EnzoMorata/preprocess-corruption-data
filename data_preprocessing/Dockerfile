FROM jupyter/base-notebook:python-3.11

# Install linux dependencies
USER root
RUN apt-get update 

# Switch to my user for jupyter
USER enzo

WORKDIR /home/enzo/work
