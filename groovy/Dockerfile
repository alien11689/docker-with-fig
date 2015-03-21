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

RUN wget http://dl.bintray.com/groovy/maven/groovy-sdk-2.4.2.zip -O /tmp/groovy.zip

RUN mkdir -p /opt/

RUN unzip /tmp/groovy.zip -d /opt/

ENV PATH /opt/groovy-2.4.2/bin/:$PATH

WORKDIR /project

CMD bash -c groovysh
