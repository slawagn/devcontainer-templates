# Same code can be found in cpp/make/blank
FROM debian:stable

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update &&   \
    apt-get install -y  \
      sudo              \
      git

RUN useradd             \
      --groups sudo     \
      --create-home     \
      --shell /bin/bash \
      code
RUN adduser code sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER code

WORKDIR /workspaces/templates/c/blank

RUN sudo apt-get install -y \
      build-essential       \
      gdb                   \
      valgrind              \
      pkg-config            \
      doxygen               \
      autoconf              \
      automake              \
      libtool

RUN sudo apt-get install -y \
      libcurl4-gnutls-dev   \
      libglib2.0-dev        \
      libgsl-dev            \
      libsqlite3-dev        \
      libxml2-dev

