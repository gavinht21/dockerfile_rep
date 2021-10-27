FROM ubuntu:20.04

#https://stackoverflow.com/questions/59692797/how-to-fill-user-input-for-interactive-command-for-run-command/68463865
#https://www.cnblogs.com/tl542475736/p/9645920.html
ENV TZ=UTC\
    DEBIAN_FRONTEND=noninteractive

#USER sandyli:docker

RUN apt-get update && apt-get install -y \
    python3-pip\
    make\
    git-all\
    curl\
#install for setfacl: command not found
    acl\
    lsb-release\
    software-properties-common\
    vim

#install docker
#RUN curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | sudo apt-key add -
RUN curl -fsSL http://mirrors.aliyun.com/docker-ce/linux/ubuntu/gpg | apt-key add -
RUN add-apt-repository "deb [arch=amd64] http://mirrors.aliyun.com/docker-ce/linux/ubuntu $(lsb_release -cs) stable"
RUN apt-get update

RUN apt-cache madison docker-ce

RUN apt-get install -y docker-ce=5:20.10.10~3-0~ubuntu-focal docker-ce-cli=5:20.10.10~3-0~ubuntu-focal containerd.io

RUN pip3 install j2cli

RUN apt-get install -y sudo

VOLUME /projects/sandyli/gavin/falcon

#create the docker group
#RUN groupadd docker

#add user, create user's home dir, set password && add to group docker
#https://stackoverflow.com/questions/27701930/how-to-add-users-to-docker-container
#RUN useradd --system --create-home --password 123456 --no-log-init --shell /bin/bash --gid docker sandyli
RUN useradd --system --create-home --no-log-init --shell /bin/bash sandyli
RUN echo "sandyli:123456" | chpasswd
#RUN usermod -G root sandyli
RUN adduser sandyli docker
RUN adduser sandyli sudo
#RUN adduser sandyli root

#USER sandyli:docker
USER sandyli

COPY daemon.json /etc/docker/
#VOLUME /projects/sandyli/gavin/falcon
#CMD  cd ./projects/sandyli/gavin/falcon
