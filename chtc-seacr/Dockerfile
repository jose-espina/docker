FROM continuumio/miniconda3
MAINTAINER jespina@wisc.edu
LABEL authors="Jose Espina" \
      description="chtc-seacr docker container for Roopra lab"

WORKDIR ./

# install (nf tracing)
RUN apt-get update && \
    apt-get install -y procps

# install R
RUN yum -y install R-core

# install conda packages
COPY conda_env.yml ./

RUN \ 
	conda env update -n root -f conda_env.yml \
	&& conda clean -a

