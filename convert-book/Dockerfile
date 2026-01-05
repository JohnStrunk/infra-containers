# syntax=docker/dockerfile:1@sha256:b6afd42430b15f2d2a4c5a02b919e98a525b785b1aaff16747d2f623364e39b6
FROM debian:stable-slim@sha256:449673e1239be6fdc89616f926abb87f360c280c3bb7ca3591694564359695fa

# hadolint ignore=DL3008
RUN apt-get update && apt-get install --no-install-recommends -y \
    calibre \
    fonts-dejavu-core \
    fonts-dejavu-extra \
    ca-certificates \
    && rm -rf /var/lib/apt/lists/*

COPY entry.sh /entry.sh
RUN chmod a+rx /entry.sh

ENTRYPOINT [ "/entry.sh" ]
