#
# Rock R Server Dockerfile with DataSHIELD Junction Xenon profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3-2.0

RUN apt-get update -y
RUN apt-get upgrade -y
RUN R -q -e "update.packages()"

ENV DSMEDIATION_VERSION 0.0.3
ENV DSEXPOSOME_VERSION 2.0.9
ENV DSOMICS_VERSION v1.0.18-2
ENV DSMTL_VERSION 0.9.9
ENV DSURVIVAL_VERSION v2.1.3

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages
# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsMediation', ref = '$DSMEDIATION_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"
# dsMTLBase
RUN Rscript -e "remotes::install_github('transbioZI/dsMTLBase', ref = '$DSMTL_VERSION', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
# dsSurvival
RUN Rscript -e "remotes::install_github('neelsoumya/dsSurvival', ref = '$DSURVIVAL_VERSION', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
# dsExposome
RUN Rscript -e "BiocManager::install(c('bumphunter', 'missMethyl', 'rexposome'), update = FALSE, ask = FALSE, lib = '$ROCK_LIB')" \
 && Rscript -e "remotes::install_github('isglobal-brge/dsExposome', ref = '$DSEXPOSOME_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"
# dsOmics
RUN Rscript -e "BiocManager::install(c('Biobase', 'SNPRelate', 'GENESIS', 'GWASTools', 'GenomicRanges', 'SummarizedExperiment', 'DESeq2', 'edgeR', 'MEAL'), update = FALSE, ask = FALSE, lib = '$ROCK_LIB')" \
 && Rscript -e "remotes::install_github('isglobal-brge/dsOmics', ref = '$DSOMICS_VERSION', upgrade = FALSE, lib = '$ROCK_LIB')"
