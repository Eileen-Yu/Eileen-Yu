FROM debian:11.2

LABEL version="0.0.1"

ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && \
  apt-get install --yes texlive-xetex

WORKDIR /data
VOLUME ["/data"]

