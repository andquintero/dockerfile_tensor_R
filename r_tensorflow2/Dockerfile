FROM rocker/tidyverse
#FROM rocker/rstudio

LABEL maintainer="Andres Quintero a.quintero@dkfz-heidelberg.de"

#RUN install2.r --error \
#    devtools


# from the tensorflow dockerfile: 
# https://github.com/tensorflow/tensorflow/blob/master/tensorflow/tools/dockerfiles/dockerfiles/cpu-jupyter.Dockerfile


ARG USE_PYTHON_3_NOT_2=True
ARG _PY_SUFFIX=${USE_PYTHON_3_NOT_2:+3}
ARG PYTHON=python${_PY_SUFFIX}
ARG PIP=pip${_PY_SUFFIX}


# See http://bugs.python.org/issue19846
ENV LANG C.UTF-8

RUN apt-get update && apt-get install -y \
    ${PYTHON} \
    ${PYTHON}-pip

RUN ${PIP} --no-cache-dir install --upgrade \
    pip \
    setuptools

# Some TF tools expect a "python" binary
RUN ln -s $(which ${PYTHON}) /usr/local/bin/python 


RUN ${PIP} install tensorflow==2.1.0

# # Pick up some TF dependencies
# RUN apt-get update && apt-get install -y --no-install-recommends \
#         build-essential \
#         curl \
#         libfreetype6-dev \
#         libzmq3-dev \
#         pkg-config \
#         python \
#         python-dev \
#         rsync \
#         software-properties-common \
#         unzip \
#         && \
#     apt-get clean && \
#     rm -rf /var/lib/apt/lists/*

# RUN curl -O https://bootstrap.pypa.io/get-pip.py && \
#     python get-pip.py && \
#     rm get-pip.py
    

# RUN pip --no-cache-dir install \
#         ipykernel \
#         jupyter \
#         matplotlib \
#         numpy \
#        scipy \
#        tensorflow==2.0.0-alpha0 \
#         && \
#     python -m ipykernel.kernelspec

    
    
#docker build -t r_tensor2 .
#docker run -e PASSWORD=bratwurst -p 8787:8787 r_tensor2