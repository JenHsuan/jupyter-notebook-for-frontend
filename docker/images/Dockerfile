FROM ubuntu:20.04

WORKDIR /app

ARG DEBIAN_FRONTEND=noninteractive

# install Python
RUN apt-get -y update \
  && apt-get -y upgrade \
  && apt-get install -y python3.7 python3-pip sudo tzdata cmake curl unzip

RUN useradd -m docker && echo "docker:docker" | chpasswd && adduser docker sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER docker

# install Jupyter
RUN sudo pip3 install notebook

# install node.js
RUN sudo apt-get install -y node.js npm \
  && sudo npm cache clean -f \
  && sudo npm i --unsafe-perm \
  && sudo npm install -g n \
  && sudo n 18.20.1

# install ijavascript
RUN sudo npm install -g ijavascript --unsafe-perm=true --allow-root
RUN sudo ijsinstall

# install tslib
RUN sudo npm install -g tslab --unsafe-perm=true --allow-root
RUN sudo tslab install

# install demo kernel
RUN sudo curl -fsSL https://deno.land/install.sh | sh
RUN sudo /home/docker/.deno/bin/deno jupyter --install

