# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.241.1/containers/ubuntu/.devcontainer/base.Dockerfile

# [Choice] Ubuntu version (use ubuntu-22.04 or ubuntu-18.04 on local arm64/Apple Silicon): ubuntu-22.04, ubuntu-20.04, ubuntu-18.04
ARG VARIANT="jammy"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
     # For Japanese env
     fontconfig fonts-noto-cjk \
     language-pack-ja-base language-pack-ja locales \
     # For common develop
     build-essential \
     # cleaning
     && apt-get clean && rm -rf /var/lib/apt/lists/*


USER vscode
SHELL ["/bin/bash", "-c"]
RUN echo 'export LANG=ja_JP.UTF-8' >> ~/.bashrc
RUN echo 'set nocompatible' >> ~/.vimrc && echo 'set backspace=indent,eol,start' >> ~/.vimrc

