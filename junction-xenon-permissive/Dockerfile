#
# Rock R Server Dockerfile with DataSHIELD Junction Xenon profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-junction-xenon:latest

ENV DSBASE_VERSION 6.3.0-permissive

# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsBase', ref = '$DSBASE_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')" && \
  chown -R rock $ROCK_LIB
