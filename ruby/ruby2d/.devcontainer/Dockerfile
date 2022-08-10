FROM ruby:bullseye

RUN apt-get update &&   \
    apt-get install -y  \
      sudo

RUN useradd             \
      --create-home     \
      --groups sudo     \
      --shell /bin/bash \
      code
RUN adduser code sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER code

RUN sudo apt-get install -y \
      libsdl2-dev           \
      libsdl2-image-dev     \
      libsdl2-mixer-dev     \
      libsdl2-ttf-dev

WORKDIR /workspaces/tinyrenderer-ruby

COPY Gemfile Gemfile.lock ./
RUN bundle install
