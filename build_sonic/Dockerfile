FROM ubuntu:20.04

#https://stackoverflow.com/questions/59692797/how-to-fill-user-input-for-interactive-command-for-run-command/68463865
#https://www.cnblogs.com/tl542475736/p/9645920.html
ENV TZ=UTC\
    DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    python3-pip\
    make\
    git-all

RUN pip3 install j2cli

VOLUME /projects/sandyli/gavin/falcon

#ENV TZ=UTC\
#    DEBIAN_FRONTEND=noninteractive

