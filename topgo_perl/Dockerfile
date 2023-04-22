FROM mambaorg/micromamba:0.13.1

COPY R-base.yml R-base_micro.yml

RUN micromamba install -y -n base -f R-base_micro.yml && \
    micromamba clean --all --yes

RUN Rscript -e "install.packages(c('BiocManager'), repos = 'https://cloud.r-project.org/')"
RUN Rscript -e "BiocManager::install('RCurl')"
RUN Rscript -e "BiocManager::install('topGO')"

#Install prcops so we can use nextflwo tower:
RUN apt-get update \
    && apt-get install -y wget \
                          procps \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*