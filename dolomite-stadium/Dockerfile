#
# Rock R Server Dockerfile with DataSHIELD Dolomite Stadium profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.2-R4.2

ENV DSMEDIATION_VERSION 0.0.3
ENV DSEXPOSOME_VERSION 2.0.4
ENV DSURVIVAL_VERSION v1.0.1

ENV ROCK_LIB /var/lib/rock/R/library

# Install new R packages
# dsMediation
RUN Rscript -e "remotes::install_github('datashield/dsMediation', ref = '$DSMEDIATION_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"
# dsSurvival
RUN Rscript -e "remotes::install_github('neelsoumya/dsSurvival', ref = '$DSURVIVAL_VERSION', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
# dsExposome
RUN Rscript -e "BiocManager::install(c('bumphunter', 'missMethyl', 'rexposome'), update = FALSE, ask = FALSE, lib = '$ROCK_LIB')" \
 && Rscript -e "remotes::install_github('isglobal-brge/dsExposome', ref = '$DSEXPOSOME_VERSION', repos = c('https://cloud.r-project.org', 'https://cran.datashield.org'), upgrade = FALSE, lib = '$ROCK_LIB')"

RUN chown -R rock $ROCK_LIB
