# [Preparation]
#
# 1. Download PGX Server file
#       from  http://www.oracle.com/technetwork/oracle-labs/parallel-graph-analytix/downloads/downloads-2206142.html .
#
# 2. Place the PGX Server file (e.g. pgx-2.7.0-server.zip) in the same folder as the Dockerfile.
#
# 3. Place PGX configuration files in the same folder as the Dockerfile if you want to change configuration.
# 
# ---------------------------------------------
FROM openjdk:8-jdk

ARG PGX_VERSION=2.7.0
ENV PGX_HOME=/opt/pgx \
    INSTALL_FILE=pgx-${PGX_VERSION}-server.zip

COPY $INSTALL_FILE $PGX_HOME/

WORKDIR $PGX_HOME
RUN apt-get install -y unzip && \
    unzip $INSTALL_FILE && \
    rm $INSTALL_FILE

WORKDIR ./pgx-${PGX_VERSION}/

# Replace configuration files if you need to.
# RUN rm ./conf/server.conf
# COPY server.conf ./conf/server.conf

CMD ./bin/pgx
