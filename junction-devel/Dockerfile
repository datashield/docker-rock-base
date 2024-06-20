#
# Rock R Server Dockerfile with DataSHIELD Junction Devel profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3.0-R4.4.0

ENV ROCK_LIB /var/lib/rock/R/library

# Install new R packages

ENV DSBASE_VERSION v6.3.1-dev

# dsBase
RUN Rscript -e "remotes::install_github('datashield/dsBase', ref = '$DSBASE_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')" && \
  chown -R rock $ROCK_LIB
