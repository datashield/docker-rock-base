#
# Rock R Server Dockerfile with DataSHIELD Dolomite Devel profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3-2.0

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages

ENV DSBASE_VERSION v6.3.1-dev

# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsBase', ref = '$DSBASE_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"
