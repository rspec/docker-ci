FROM rspec/ci:rvm

RUN /bin/bash -l -c "rvm install jruby-1.7"

ENV PATH=/usr/local/rvm/rubies/jruby-1.7.27/bin:$PATH

RUN ruby -v

RUN gem update --system '2.7.11'

RUN gem -v

RUN gem install bundler -v '1.17.3'

RUN ln -s /usr/local/rvm/rubies/jruby-1.7.27/bin/bundler /usr/bin/bundler

RUN bundler -v

CMD ["/bin/bash"]
