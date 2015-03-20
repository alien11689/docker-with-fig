FROM ubuntu:14.10

MAINTAINER alien11689@gmail.com

RUN apt-get update

RUN apt-get upgrade -y 

VOLUME /project

WORKDIR /project

RUN apt-get install -y haskell-platform hlint

CMD bash -c ghci
