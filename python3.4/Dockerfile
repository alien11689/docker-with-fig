FROM ubuntu:14.10

MAINTAINER alien11689@gmail.com

RUN apt-get update 

RUN apt-get upgrade -y 

VOLUME /project

WORKDIR /project

RUN apt-get install -y python3.4

CMD bash -c python3.4
