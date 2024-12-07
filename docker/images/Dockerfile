FROM ubuntu:22.04

WORKDIR /app

ARG DEBIAN_FRONTEND=noninteractive

# install Python
RUN apt-get -y update \
  && apt-get -y upgrade \
  && apt-get install -y python3.10 python3-pip sudo tzdata cmake curl unzip tar

RUN useradd -m docker && echo "docker:docker" | chpasswd && adduser docker sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER docker

# install Jupyter
RUN sudo pip3 install notebook

# install node.js
RUN sudo apt-get install -y node.js npm \
  && sudo npm cache clean -f \
  && sudo npm install -g n \
  && sudo n 20.9.0

# install ijavascript
RUN sudo npm install -g ijavascript@5.2.1 --unsafe-perm=true --allow-root
RUN sudo ijsinstall

# install tslib
RUN sudo npm install -g tslab@1.0.22 --unsafe-perm=true --allow-root
RUN sudo tslab install

# install demo kernel
RUN sudo curl -fsSL https://deno.land/install.sh | sh
RUN sudo /home/docker/.deno/bin/deno jupyter --install

