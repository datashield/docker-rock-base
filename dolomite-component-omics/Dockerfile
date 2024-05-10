#
# Rock R Server Dockerfile with DataSHIELD dolomite omics component
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3

ENV DSOMICS_VERSION v1.0.18-2

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages
# dsOmics
RUN Rscript -e "BiocManager::install(c('Biobase', 'SNPRelate', 'GENESIS', 'GWASTools', 'GenomicRanges', 'SummarizedExperiment', 'DESeq2', 'edgeR', 'MEAL'), update = FALSE, ask = FALSE, lib = '$ROCK_LIB')" \
 && Rscript -e "remotes::install_github('isglobal-brge/dsOmics', ref = '$DSOMICS_VERSION', upgrade = FALSE, lib = '$ROCK_LIB')"
