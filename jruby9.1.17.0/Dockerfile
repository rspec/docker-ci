FROM rspec/ci:rvm

RUN /bin/bash -l -c "rvm install jruby-9.1.17.0"

ENV PATH=/usr/local/rvm/rubies/jruby-9.1.17.0/bin:$PATH

RUN ruby -v

RUN yes | gem update --system '2.7.11'

RUN gem -v

RUN yes | gem install bundler -v '1.17.3'

RUN ln -s /usr/local/rvm/rubies/jruby-9.1.17.0/bin/bundler /usr/bin/bundler

RUN bundler -v

CMD ["/bin/bash"]
