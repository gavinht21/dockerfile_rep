FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
    python3-pip\
    make

RUN pip3 install j2cli

#source code path on host
VOLUME /projects/sandyli/gavin/falcon
