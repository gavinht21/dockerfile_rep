FROM ubuntu:20.04

#https://stackoverflow.com/questions/59692797/how-to-fill-user-input-for-interactive-command-for-run-command/68463865
#https://www.cnblogs.com/tl542475736/p/9645920.html
ENV TZ=UTC\
    DEBIAN_FRONTEND=noninteractive

#USER sandyli:docker

RUN apt-get update && apt-get install -y \
    python3-pip\
    make\
    git-all

RUN pip3 install j2cli

VOLUME /projects/sandyli/gavin/falcon

#create the docker group
RUN groupadd docker

#add user, create user's home dir, set password && add to group docker
#https://stackoverflow.com/questions/27701930/how-to-add-users-to-docker-container
RUN useradd --system --create-home --password 123456 --no-log-init --shell /bin/bash --gid docker sandyli

USER sandyli:docker

#CMD  cd ./projects/sandyli/gavin/falcon
