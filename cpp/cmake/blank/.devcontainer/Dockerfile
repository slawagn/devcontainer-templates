# Same code can be found in cpp/make/blank
FROM debian:stable

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update &&   \
    apt-get install -y  \
      sudo              \
      git

RUN useradd         \
      --create-home     \
      --groups sudo \
      --shell /bin/bash \
      code
RUN adduser code sudo
RUN echo '%sudo ALL=(ALL) NOPASSWD:ALL' >> /etc/sudoers
USER code

RUN sudo apt-get install -y \
      build-essential       \
      gdb

# Installing Cmake
RUN sudo apt-get install -y  \
      gpg                    \
      wget

RUN wget -O - https://apt.kitware.com/keys/kitware-archive-latest.asc \
      2>/dev/null                                                     \
      | gpg --dearmor -                                               \
      | sudo tee /usr/share/keyrings/kitware-archive-keyring.gpg      \
      >/dev/null

RUN echo 'deb [signed-by=/usr/share/keyrings/kitware-archive-keyring.gpg] \
    https://apt.kitware.com/ubuntu/ focal main' \
    | sudo tee /etc/apt/sources.list.d/kitware.list \
    >/dev/null

RUN sudo apt-get update &&  \
    sudo apt-get install -y \
      cmake                 \
      build-essential       \
      gdb
