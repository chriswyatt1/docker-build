FROM mambaorg/micromamba:0.13.1

ARG datasets_version="v16.1.2"
ARG datasets_architecture="linux-arm64" # linux-arm64 

COPY conda.yml conda.here.yml

RUN apt-get update \
    && apt-get install -y wget procps unzip \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

RUN micromamba install -y -n base -f conda.here.yml && \
    micromamba clean --all --yes

