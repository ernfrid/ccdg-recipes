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
    zlib1g \
    zlib1g-dev \
    --no-install-recommends

WORKDIR /build

# Import resources
COPY ./Makefile /build

CMD make
