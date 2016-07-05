FROM ubuntu:16.04
MAINTAINER Scott Brown

RUN apt-get update -qq && apt-get dist-upgrade -y
RUN apt-get install -y curl

RUN curl https://storage.googleapis.com/golang/go1.6.2.linux-amd64.tar.gz | tar -v -C /usr/local -xz

RUN mkdir -p /go/src

ENV PATH /usr/local/go/bin:/go/bin:$PATH
ENV GOPATH /go

ENTRYPOINT ["go"]

