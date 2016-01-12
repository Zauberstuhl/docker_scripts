FROM debian:jessie
MAINTAINER Lukas Matt <lukas@zauberstuhl.de>

ENV DEBIAN_FRONTEND noninteractive

#
## dependencies
#

RUN apt-get update && apt-get install -y apt-transport-https
# sbt source
RUN echo "deb https://dl.bintray.com/sbt/debian /" | tee -a /etc/apt/sources.list.d/sbt.list
RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 642AC823
RUN apt-get update && apt-get install -y default-jdk sbt git-core
RUN apt-get clean && apt-get autoclean
