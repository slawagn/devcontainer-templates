# Same code can be found in debian/blank/Dockerfile 
FROM debian:stable

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update &&   \
    apt-get install -y  \
      sudo              \
      git

RUN useradd             \
      --groups sudo     \
      --shell /bin/bash \
      code
RUN adduser code sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER code

# Installing Make

RUN sudo apt-get install -y \
      build-essential       \
      gdb
