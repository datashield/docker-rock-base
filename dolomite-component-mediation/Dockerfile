#
# Rock R Server Dockerfile with DataSHIELD dolomite mediation component
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3

ENV DSMEDIATION_VERSION 0.0.3

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages
# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsMediation', ref = '$DSMEDIATION_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"
