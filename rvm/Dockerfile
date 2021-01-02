FROM ubuntu:20.04

ENV LANG C.UTF-8

RUN apt-get update

# This is necessary because tzdata asks for a timezone
RUN DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends tzdata

RUN apt-get install -y software-properties-common build-essential curl

RUN \
  add-apt-repository ppa:git-core/ppa && \
  apt update && \
  apt install -y git

RUN git --version

RUN curl -sSL https://get.rvm.io | bash

RUN usermod -a -G rvm root


# This adds the legacy libss1.0-dev package needed for old rubies
RUN echo "deb http://security.ubuntu.com/ubuntu bionic-security main" >> /etc/apt/sources.list
RUN apt update && apt-get install -y libssl1.0-dev

RUN /bin/bash -l -c "rvm requirements"

CMD ["/bin/bash"]
