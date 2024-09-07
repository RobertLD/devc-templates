ARG imageVariant=${imageVariant}
FROM mcr.microsoft.com/devcontainers/base:${imageVariant}

# Avoid warnings by switching to noninteractive
ARG DEBIAN_FRONTEND=noninteractive
ARG sdkVersion=${sdkVersion}
RUN apt-get install -y


RUN apt-get update \
    && apt-get -y upgrade \
    && apt-get install -y \
    curl \
    git \
    unzip \
    xz-utils \
    zip \
    libglu1-mesa \
    libc6:amd64 \
    libstdc++6:amd64 \
    libbz2-1.0:amd64 \
    libncurses5:amd64 \
    wget \ 
    unzip \ 
    cmake


RUN wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${sdkVersion}-stable.tar.xz
RUN tar -xf flutter_linux_${sdkVersion}-stable.tar.xz -C /usr/local
ENV PATH="${PATH}:/usr/local/flutter/bin"
