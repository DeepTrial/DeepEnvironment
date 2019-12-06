FROM nvidia/cuda:9.2-cudnn7-runtime-ubuntu16.04

MAINTAINER resnick.xing@foxmail.com

RUN apt-get update && apt-get install -y \
	wget \
	vim \
	bzip2

#Downgrade CUDA, TF issue: https://github.com/tensorflow/tensorflow/issues/17566#issuecomment-372490062
RUN apt-get install --allow-downgrades -y libcudnn7=7.0.5.15-1+cuda9.0

#Install MINICONDA
RUN wget https://repo.continuum.io/miniconda/Miniconda3-4.3.30-Linux-x86_64.sh -O Miniconda.sh && \
	/bin/bash Miniconda.sh -b -p /opt/conda && \
	rm Miniconda.sh

ENV PATH /opt/conda/bin:$PATH

#Install ANACONDA Environment
#RUN conda install pytorch torchvision cudatoolkit=9.2 -c pytorch && conda install -c menpo opencv3
RUN conda install -c menpo opencv3 && conda install jupyterlab
#Launch JUPYTER COMMAND
#CMD jupyter notebook --ip=* --no-browser --allow-root --notebook-dir=/tmp

