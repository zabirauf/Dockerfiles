FROM ubuntu:12.04
MAINTAINER Zohaib Rauf <zabirauf@gmail.com>

# Setting locale as Elixir is choosy about it
RUN locale-gen en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

RUN apt-get update && apt-get -y install wget curl git g++ libssl-dev libncurses5-dev bc python unzip libc6:i386 libstdc++6:i386 zlib1g:i386 gcc-multilib make bzip2 m4

RUN mkdir ~/.nerves-cache; mkdir /Downloads
WORKDIR /Downloads

RUN git clone https://github.com/nerves-project/nerves-sdk.git; cd nerves-sdk; make nerves_rpi_elixir_defconfig
RUN cd nerves-sdk; make
