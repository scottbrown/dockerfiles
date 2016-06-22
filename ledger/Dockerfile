FROM ubuntu:16.04
MAINTAINER Scott Brown

RUN  apt-get update -qq \
  && apt-get dist-upgrade -y \
  && apt-get install -y ledger \
  && apt-get clean -y \
  && apt-get autoclean -y \
  && apt-get autoremove -y \
  && rm -rf /var/lib/apt-lists/*

ENTRYPOINT ["ledger"]

