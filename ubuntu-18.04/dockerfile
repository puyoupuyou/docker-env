FROM ubuntu:18.04
LABEL mantainer="ding_zhao@megahuntmicro.com" \
      vendor="Megahunt" \
      description="Container with everything needed to run MH1905 SDK"

ARG DEBIAN_FRONTEND=noninteractive


# Ubuntu18.04 tsinghua apt mirror 
RUN  cp /etc/apt/sources.list /etc/apt/sources.list.backup
#COPY apt-sources.list /etc/apt/sources.list

RUN yes | unminimize

# apt things
RUN apt update

RUN apt install -y --no-install-recommends \
  systemd sudo apt-utils locales curl
  
RUN systemctl mask systemd0resolved.service

RUN apt install -y --no-install-recommends \
        bash-completion \
        bc \
        bison \
        build-essential \
        cpio \
        flex \
        gawk \
        gcc \
        gdisk \
        git \
        gnupg \
        gperf \
        groff \
        g++-multilib \
        libc6-dev \
        lib32ncurses5-dev \
        libnet-ifconfig-wrapper-perl \
        lib32z1-dev \
        libgl1-mesa-dev \
        libx11-dev \
        libxml2-utils \
        make \
        zsh \
        vim \
  openssh-server \
  python3 \
  python3.7\
  python3 \
        python3-flake8 \
        python3-nose2 \
        python3-pexpect \
        openjdk-8-jdk \
  tofrodos \
  unzip \
        wget \
        zlib1g-dev \
  xsltproc \  
        x11proto-core-dev \
        zip \
        && \
    apt -y autoremove && \
    apt -y clean
    
#Language setting
RUN sed -i 's/# \(en_US.UTF-8\)/\1/' /etc/locale.gen && \
    /usr/sbin/locale-gen
RUN sed -i 's/# \(zh_CN.UTF-8\)/\1/' /etc/locale.gen && \
    /usr/sbin/locale-gen

#RUN locale-gen en_US.UTF-8
#RUN locale-gen zh_CN.UTF-8

ENV LC_ALL en_US.UTF-8

# python3 and repo 
RUN ln -s /usr/bin/python3.7 /usr/bin/python
RUN curl https://mirrors.tuna.tsinghua.edu.cn/git/git-repo -o ./repo
RUN chmod +x ./repo
RUN mv ./repo /usr/local/bin


CMD [ "systemd" ]
