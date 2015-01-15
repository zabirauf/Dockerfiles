FROM ubuntu:14.04
MAINTAINER Zohaib Rauf <zabirauf@gmail.com>

# Setting locale as Elixir is choosy about it
RUN locale-gen en_US.UTF-8
ENV LANGUAGE en_US.UTF-8
ENV LANG en_US.UTF-8
ENV LC_ALL en_US.UTF-8

RUN apt-get update && apt-get -y install wget curl

RUN echo "deb http://packages.erlang-solutions.com/ubuntu precise contrib" >> /etc/apt/sources.list

RUN mkdir /Downloads
WORKDIR /Downloads

RUN wget http://packages.erlang-solutions.com/ubuntu/erlang_solutions.asc
RUN apt-key add erlang_solutions.asc
RUN apt-get update && apt-get -y install erlang git make && mkdir /Applications

WORKDIR /Applications
RUN git clone https://github.com/elixir-lang/elixir.git
WORKDIR elixir

RUN git checkout v1.0.2 && make clean test

ENV PATH $PATH:/Applications/elixir/bin
