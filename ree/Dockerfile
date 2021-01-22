FROM rspec/ci:rvm

RUN /bin/bash -l -c "rvm install ree"

ENV PATH=/usr/local/rvm/rubies/ree-1.8.7-2012.02/bin:$PATH

RUN ruby -v

RUN curl https://rubygems.org/downloads/rubygems-update-2.7.11.gem > rubygems-update-2.7.11.gem
RUN gem install rubygems-update-2.7.11.gem
RUN /usr/local/rvm/rubies/ree-1.8.7-2012.02/bin/update_rubygems
RUN rm rubygems-update-2.7.11.gem

RUN gem -v

RUN curl https://rubygems.org/downloads/bundler-1.17.3.gem > bundler-1.17.3.gem
RUN gem install --force bundler-1.17.3.gem
RUN rm bundler-1.17.3.gem

RUN bundler -v

CMD ["/bin/bash"]
