FROM mambaorg/micromamba:0.13.1

COPY conda.yml conda.here.yml

RUN apt-get update \
    && apt-get install -y wget \
                          procps \
                          gcc \
                          make \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*


RUN micromamba install -y -n base -f conda.here.yml && \
    micromamba clean --all --yes

RUN wget -c https://github.com/yeban/flo/archive/master.tar.gz -O flo.tar.gz
RUN tar xvf flo.tar.gz
RUN mv flo-master flo
RUN /flo/scripts/install.sh