FROM jenkins:latest

USER root

RUN  mkdir -p /app/work/


RUN curl -fsSLO https://get.docker.com/builds/Linux/x86_64/docker-17.04.0-ce.tgz \
  && tar xzvf docker-17.04.0-ce.tgz \
  && mv docker/docker /usr/local/bin \
  && rm -r docker docker-17.04.0-ce.tgz

RUN apt-get update

RUN apt-get update && apt-get install -y --no-install-recommends apt-utils

RUN apt-get install git

