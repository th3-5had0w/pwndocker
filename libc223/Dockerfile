FROM ubuntu:16.04

ENV DEBIAN_FRONTEND noninteractive

ENV TZ Asia/Shanghai

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
    # python3-distutils \
    bison \
    rpm2cpio cpio \
    zstd \
    tzdata --fix-missing && \
    rm -rf /var/lib/apt/list/*

RUN apt-add-repository ppa:brightbox/ruby-ng -y && \
    apt update -y && \
    apt-get install ruby2.4 ruby2.4-dev -y

RUN ln -fs /usr/share/zoneinfo/$TZ /etc/localtime && \
    dpkg-reconfigure -f noninteractive tzdata

RUN python3 -m pip install pip==20.3.3 && \
    python3 -m pip install --no-cache-dir pwntools ropgadget

RUN gem install one_gadget seccomp-tools

RUN cd ~/ && git clone --depth 1 https://github.com/pwndbg/pwndbg && \
    cd pwndbg && chmod +x setup.sh && ./setup.sh

RUN git clone --depth 1 https://github.com/scwuaptx/Pwngdb.git ~/Pwngdb && \
    cd ~/Pwngdb && cat ~/Pwngdb/.gdbinit  >> ~/.gdbinit && \
    sed -i "s?source ~/peda/peda.py?# source ~/peda/peda.py?g" ~/.gdbinit

ENV LANG C.UTF-8

RUN mkdir /ctf
WORKDIR /ctf
CMD ["/bin/bash"]
