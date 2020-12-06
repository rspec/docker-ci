# RSpec Docker Images

Base images for testing RSpec on legacy Rubies.

This is not recommended for use.

## Build Instructions

1 - `docker build <target>`
2 - `docker tag <result of 1> rspec/ci:<target>`
3 - `docker push rspec/ci:<target>`
