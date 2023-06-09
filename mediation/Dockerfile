#
# Rock R Server Dockerfile with DataSHIELD Mediation
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.2-R4.3

ENV DSMEDIATION_VERSION 0.0.3

ENV ROCK_LIB /var/lib/rock/R/library

# Install new R packages
# medflex
RUN Rscript -e "remotes::install_github('jmpsteen/medflex', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsMediation', ref = '$DSMEDIATION_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"


RUN chown -R rock $ROCK_LIB
