FROM rspec/ci:rvm

RUN /bin/bash -l -c "rvm install 1.9.2 || echo \"Rubygems is expected to fail\""

ENV PATH=/usr/local/rvm/rubies/ruby-1.9.2-p330/bin:$PATH

RUN ruby -v

RUN curl https://rubygems.org/downloads/rubygems-update-2.7.11.gem > rubygems-update-2.7.11.gem
RUN gem install rubygems-update-2.7.11.gem
RUN update_rubygems
RUN rm rubygems-update-2.7.11.gem

RUN gem -v

RUN curl https://rubygems.org/downloads/bundler-1.17.3.gem > bundler-1.17.3.gem
RUN gem install --force bundler-1.17.3.gem
RUN rm bundler-1.17.3.gem

RUN bundler -v

CMD ["/bin/bash"]
