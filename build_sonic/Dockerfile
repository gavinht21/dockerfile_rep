FROM ubuntu:20.04

RUN apt-get update && apt-get install -y \
    python3-pip\
    make\
    git-all

RUN pip3 install j2cli

#source code path on host
VOLUME /projects/sandyli/gavin/falcon

#https://www.cnblogs.com/tl542475736/p/9645920.html
ENV DEBIAN_FRONTEND=noninteractive
