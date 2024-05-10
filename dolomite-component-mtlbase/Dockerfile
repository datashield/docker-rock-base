#
# Rock R Server Dockerfile with DataSHIELD dolomite mtlbase component
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3

ENV DSMTL_VERSION 0.9.9

ENV ROCK_LIB /var/lib/rock/R/library
RUN chown rock $ROCK_LIB
RUN chmod +t $ROCK_LIB

# Install new R packages
# dsMTLBase
RUN Rscript -e "remotes::install_github('transbioZI/dsMTLBase', ref = '$DSMTL_VERSION', dependencies = TRUE, upgrade = FALSE, lib = '$ROCK_LIB')"
