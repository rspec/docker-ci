# RSpec Docker Images

Base images for testing RSpec on legacy Rubies.

This is not recommended for use.


## Setup Instructions

["Create a "classic" personal access](https://github.com/settings/tokens/new) token with the following permissions:

- write:packages
- read:packages
- delete:packages

Its recommended you have an expiry on this token, so remember to refresh it before pushing images.

Login to the Github Container Registry (GHCR) with your token, e.g.

```
export CR_PAT=`pbpaste`
echo $CR_PAT | docker login ghcr.io -u <YourUser> --password-stdin
```

Note how you pass the token to docker is up to you, this is just an example.

## Build Instructions

1) `docker build <target>`
2) Optionally `se `docker image` to find sha for step 3 if you missed it in the build output.
3) `docker tag <sha from step 1/2> ghcr.io/rspec/docker-ci:<target>`
4) `docker push ghcr.io/rspec/docker-ci:<target>`
