# Docker Image for `vimeo/psalm`

This repository contains everything to build a simple Docker image to run [Psalm](https://github.com/vimeo/psalm/). The image will also include a few Psalm plugins.

## Running the Published Image

The resulting image is published at https://ghcr.io/webfactory/psalm.

To use it: `docker run -it --rm --init -v $(pwd):/app ghcr.io/webfactory/psalm`, possibly followed by `psalm` arguments and options.

If you want to use `psalm-plugin` to list, enable or otherwise deal with plugins, use:

`docker run -it --rm --init -v $(pwd):/app --entrypoint=psalm-plugin ghcr.io/webfactory/psalm`, possibly followed by `psalm-plugin` arguments and options.

## Building the Image yourself

Review and/or tweak the `Dockerfile` as necessary.

Then, run `docker build -t psalm .`.

To use your own image, use `psalm` instead of `ghcr.io/webfactory/psalm` in the commands from the previous section.

## Building for GCHR.io

This is how we build and publish the image on the GitHub Container Registry (ghcr.io).

`docker build --label org.opencontainers.image.source=https://github.com/webfactory/docker-psalm -t ghcr.io/webfactory/psalm:latest .`

`docker push ghcr.io/webfactory/psalm:latest`


