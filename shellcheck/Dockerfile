FROM ubuntu:16.04
MAINTAINER Scott Brown

RUN apt-get update -qq \
  && apt-get install -y shellcheck \
  && apt-get clean -y \
  && apt-get autoclean -y \
  && apt-get autoremove -y \
  && rm -rf /var/lib/apt/lists/*

ENTRYPOINT ["shellcheck"]

