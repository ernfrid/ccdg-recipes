FROM ubuntu:14.04
LABEL maintainer="Dave Larson <delarson@wustl.edu"

# Volumes
VOLUME /build
VOLUME /release

# bootstrap build dependencies
RUN apt-get update -qq && \
    apt-get -y install apt-transport-https && \
    apt-get update -qq && \
    apt-get -y install \
    build-essential \
    debhelper \
    ca-certificates \
    curl \
    gfortran-4.8 \
    libatlas-dev \
    libatlas-base-dev \
    libblas-dev \
    libblas3 \
    liblapack-dev \
    liblapack3 \
    --no-install-recommends

WORKDIR /build

# Import resources
COPY ./Makefile /build

CMD make
