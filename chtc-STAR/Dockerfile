FROM continuumio/miniconda3

WORKDIR ./

# install (nf tracing)
RUN apt-get update && \
    apt-get install -y \
	procps \
	g++ \
	wget \
	libz-dev \
	make

# install conda packages
COPY conda_env.yml ./

RUN \ 
	conda env update -n root -f conda_env.yml \
	&& conda clean -a

WORKDIR \
RUN wget -nv https://github.com/alexdobin/STAR/archive/2.7.11b.tar.gz \
	&& tar xzf 2.7.11b.tar.gz && cd STAR-2.7.11b/source \
	&& make STAR STARlong && make install \
ENV PATH=/STAR-2.7.11b/bin:${PATH}
