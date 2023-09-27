FROM ubuntu:20.04

ENV DEBIAN_FRONTEND=noninteractive
RUN apt -y update
RUN apt -y install git wget gpg sudo software-properties-common dirmngr apt-transport-https lsb-release ca-certificates gcc g++
RUN git clone https://github.com/matthewbdwyer/tipc.git /tmp/tipc

WORKDIR /tmp/tipc
RUN ./bin/bootstrap.sh

WORKDIR /
RUN rm -fr /tmp/tipc


ENTRYPOINT /usr/bin/bash
