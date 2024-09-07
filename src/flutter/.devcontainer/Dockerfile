ARG imageVariant=${imageVariant}
FROM mcr.microsoft.com/devcontainers/base:${imageVariant}

# Avoid warnings by switching to noninteractive
ARG DEBIAN_FRONTEND=noninteractive
ARG flutterSdkVersion=${flutterSdkVersion}

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
    cmake \
    android-sdk \
    && rm -rf /var/lib/apt/lists/* \
    && apt-get clean



# Flutter SDK installation
RUN wget https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${flutterSdkVersion}-stable.tar.xz
RUN tar -xf flutter_linux_${flutterSdkVersion}-stable.tar.xz -C /usr/local
ENV PATH="${PATH}:/usr/local/flutter/bin"
