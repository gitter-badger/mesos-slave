FROM ubuntu:14.04

RUN apt-key adv --keyserver keyserver.ubuntu.com --recv E56151BF && echo deb http://repos.mesosphere.io/ubuntu trusty main > /etc/apt/sources.list.d/mesosphere.list && apt-get update && apt-get -y install mesos=0.22.1-1.0.ubuntu1404

RUN apt-get install -y wget && wget -qO- https://get.docker.com/ | sh

RUN apt-get install -y curl

CMD ["/usr/sbin/mesos-slave"]

ENV MESOS_WORK_DIR /tmp/mesos
ENV MESOS_CONTAINERIZERS docker,mesos

VOLUME /tmp/mesos
