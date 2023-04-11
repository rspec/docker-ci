FROM ubuntu:16.04

ENV LANG C.UTF-8

RUN \
  apt-get update && \
  apt-get install -y software-properties-common build-essential

RUN \
  add-apt-repository ppa:git-core/ppa && \
  apt update && \
  apt install -y git

RUN git --version

RUN \
  apt-add-repository ppa:brightbox/ruby-ng && \
  apt-get update && \
  apt-get install -y ruby2.1 ruby2.1-dev ruby2.1-doc

RUN ruby -v

RUN apt-get update && apt-get upgrade -y

RUN REALLY_GEM_UPDATE_SYSTEM='Yes' gem update --system '2.7.11'

RUN gem -v

RUN gem install bundler -v '1.17.3'

RUN bundler -v

CMD ["/bin/bash"]
