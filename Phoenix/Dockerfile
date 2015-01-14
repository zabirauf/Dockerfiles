FROM ubuntu:14.04
MAINTAINER Zohaib Rauf <zabirauf@gmail.com>

#RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty main restricted universe multiverse" >> /etc/apt/sources.list
#RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty-security main restricted universe multiverse" >> /etc/apt/sources.list
#RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty-updates main restricted universe multiverse" >> /etc/apt/sources.list
#RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty-proposed main restricted universe multiverse" >> /etc/apt/sources.list
#RUN echo "deb http://archive.ubuntu.com/ubuntu/ trusty-backports main restricted universe multiverse" >> /etc/apt/sources.list

RUN apt-get update && apt-get -y install wget curl

#RUN apt-get -y install software-properties-common && add-apt-repository universe

RUN echo "deb http://packages.erlang-solutions.com/ubuntu precise contrib" >> /etc/apt/sources.list

RUN mkdir ~/Downloads
WORKDIR ~/Downloads

RUN wget http://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
RUN apt-key add erlang_solutions.asc
RUN apt-get update && apt-get -y install erlang git && mkdir ~/Applications
WORKDIR ~/Applications

RUN git clone https://github.com/elixir-lang/elixir.git

WORKDIR ~/Applications/elixir

RUN make clean test

