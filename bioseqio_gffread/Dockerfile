FROM mambaorg/micromamba:0.13.1

COPY R-base.yml R-base_micro.yml

RUN apt-get update \
    && apt-get install -y wget \
                          build-essential \
                          cmake \
                          curl \
                          procps \
                          gcc \
                          make \
                          libkrb5-3 \
                          libcurl4-openssl-dev \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*


RUN micromamba install -y -n base -f R-base_micro.yml && \
    micromamba clean --all --yes

