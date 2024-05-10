#
# Rock R Server Dockerfile with DataSHIELD dolomite survival component
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3

ENV DSURVIVAL_VERSION v2.1.3

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages
# dsSurvival
RUN Rscript -e "remotes::install_github('neelsoumya/dsSurvival', ref = '$DSURVIVAL_VERSION', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
