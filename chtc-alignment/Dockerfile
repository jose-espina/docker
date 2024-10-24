FROM continuumio/miniconda3
MAINTAINER jespina@wisc.edu
LABEL authors="Jose Espina" \
      description="chtc-alignment docker container for Roopra lab"

WORKDIR ./

# copy the picard.jar file into image
# COPY picard.jar ./

# install (nf tracing)
RUN apt-get update && \
    apt-get install -y procps

# install conda packages
COPY conda_env.yml ./

RUN \ 
	conda env update -n root -f conda_env.yml \
	&& conda install anaconda::java-1.8.0-openjdk-devel-cos7-s390x \
	&& conda clean -a

