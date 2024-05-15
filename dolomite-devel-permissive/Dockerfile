#
# Rock R Server Dockerfile with DataSHIELD Dolomite Devel Permissive profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-dolomite-devel:latest

ENV DSBASE_VERSION v6.3.1-dev-permissive

# dsBase
RUN Rscript -e "remotes::install_github('datashield/dsBase', ref = '$DSBASE_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')" && \
  chown -R rock $ROCK_LIB
