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

RUN wget http://downloads.typesafe.com/scala/2.11.6/scala-2.11.6.tgz?_ga=1.190564843.1707093015.1424293818 -O /tmp/scala.tar.gz

RUN mkdir -p /opt/

RUN tar -xvzf /tmp/scala.tar.gz -C /opt/

ENV PATH /opt/scala-2.11.6/bin/:$PATH

WORKDIR /project

CMD bash -c scala
