FROM ubuntu:16.04

ARG DEBIAN_FRONTEND=noninteractive

ENV LANG C.UTF-8

RUN dpkg --add-architecture i386 && \
    apt-get -y update && \
    apt install -y \
    libc6:i386 \
    libc6-dbg:i386 \
    libc6-dbg \
    lib32stdc++6 \
    g++-multilib \
    cmake \
    ipython3 \
    vim \
    net-tools \
    iputils-ping \
    libffi-dev \
    libssl-dev \
    python3-dev \
    python3-pip \
    build-essential \
    ruby \
    ruby-dev \
    tmux \
    strace \
    ltrace \
    nasm \
    wget \
    gdb \
    gdb-multiarch \
    netcat \
    socat \
    git \
    patchelf \
    gawk \
    file \
    software-properties-common \
    bison \
    rpm2cpio cpio \
    zstd \
    tzdata --fix-missing && \
    rm -rf /var/lib/apt/list/*

RUN apt-add-repository ppa:brightbox/ruby-ng -y && \
    apt update -y && \
    apt-get install ruby2.4 ruby2.4-dev -y

RUN python3 -m pip install pip==20.3.3 && \
    python3 -m pip install --no-cache-dir pwntools ropgadget

RUN gem install one_gadget seccomp-tools

RUN cd ~/ && git clone https://github.com/pwndbg/pwndbg && \
    cd pwndbg && git checkout 2021.06.22 && chmod +x setup.sh && ./setup.sh

RUN mkdir /workspace

WORKDIR /workspace
