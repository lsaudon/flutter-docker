# syntax=docker/dockerfile:1

FROM debian:stable-slim

ARG FLUTTER_VERSION

ENV DEBIAN_FRONTEND=noninteractive \
    FLUTTER_HOME=/opt/flutter

ENV PATH="${FLUTTER_HOME}/bin:${PATH}"

RUN apt-get update \
   && apt-get install -y --no-install-recommends \
       ca-certificates \
       curl \
       git \
       make \
       unzip \
       xz-utils \
       zip \
       libglu1-mesa \
   && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL \
      "https://storage.googleapis.com/flutter_infra_release/releases/stable/linux/flutter_linux_${FLUTTER_VERSION}-stable.tar.xz" \
      -o /tmp/flutter.tar.xz \
   && tar -xf /tmp/flutter.tar.xz -C /opt \
   && rm /tmp/flutter.tar.xz \
   && git config --system --add safe.directory "${FLUTTER_HOME}" \
   && flutter --version

WORKDIR /workspace
