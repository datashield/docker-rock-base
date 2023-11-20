#
# Rock R Server Dockerfile with DataSHIELD Dolomite Aquaduct profile
#
# https://github.com/datashield/docker-rock
#

FROM datashield/rock-base:6.3-R4.3

ENV ROCK_LIB /var/lib/rock/R/library

# Install new R packages

RUN chown -R rock $ROCK_LIB
