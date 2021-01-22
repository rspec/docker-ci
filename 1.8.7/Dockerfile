FROM ubuntu:14.04

RUN \
  apt-get update && \
  apt-get install -y software-properties-common build-essential curl

RU \
  add-apt-repository ppa:git-core/ppa && \
  apt update && \
  apt install -y git

RUN \
  apt-add-repository ppa:brightbox/ruby-ng-experimental && \
  apt-get update && \
  apt-get install -y ruby1.8 ruby1.8-dev

RUN ruby -v

RUN curl https://rubygems.org/downloads/rubygems-update-2.7.11.gem > rubygems-update-2.7.11.gem
RUN gem install rubygems-update-2.7.11.gem
RUN update_rubygems
RUN rm rubygems-update-2.7.11.gem

RUN gem -v

RUN curl https://rubygems.org/downloads/bundler-1.17.3.gem > bundler-1.17.3.gem
RUN gem install --force bundler-1.17.3.gem
RUN rm bundler-1.17.3.gem

RUN bundle config --global ssl_verify_mode 0

RUN bundler -v

CMD ["/bin/bash"]
