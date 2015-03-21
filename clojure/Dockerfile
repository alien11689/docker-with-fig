FROM ubuntu:14.10

MAINTAINER alien11689@gmail.com

RUN apt-get update

RUN apt-get upgrade -y

RUN apt-get install -y wget python-software-properties software-properties-common unzip

RUN \
  echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | debconf-set-selections && \
  add-apt-repository -y ppa:webupd8team/java && \
  apt-get update && \
  apt-get install -y oracle-java8-installer && \
  rm -rf /var/lib/apt/lists/* && \
  rm -rf /var/cache/oracle-jdk8-installer

ENV JAVA_HOME /usr/lib/jvm/java-8-oracle

VOLUME /project

RUN wget https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein -O /bin/lein

RUN chmod a+x /bin/lein

RUN mkdir /lein

ENV LEIN_ROOT /lein/

RUN lein repl

WORKDIR /project

CMD lein repl
