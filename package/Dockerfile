FROM debian:testing

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys F6F88286 \
  && echo 'deb     http://ppa.launchpad.net/hvr/ghc/ubuntu trusty main' >> /etc/apt/sources.list.d/haskell.list \
  && echo 'deb-src http://ppa.launchpad.net/hvr/ghc/ubuntu trusty main' >> /etc/apt/sources.list.d/haskell.list

RUN apt-get update && apt-get install -y libgmp-dev g++ libtinfo5

ADD ghc-head/ /opt/ghc/head

RUN useradd -m -d /home/stack -s /bin/bash stack
RUN mkdir /etc/sudoers.d
RUN echo "stack ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/stack && chmod 0440 /etc/sudoers.d/stack

ENV PATH /opt/ghc/head/bin:$PATH

USER stack
WORKDIR /home/stack
RUN mkdir .stack