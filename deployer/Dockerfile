FROM debian:stable-slim@sha256:b3ef39b8a45ee3b689c462dfa711454bcfc9c9965fe81c6cfb7ff4029b5b8cd7

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
# hadolint ignore=DL3008
RUN apt-get update && apt-get install --no-install-recommends -y \
    ca-certificates \
    curl \
    gnupg \
    && rm -rf /var/lib/apt/lists/*

# Install Docker client
# hadolint ignore=DL3008,SC1091
RUN set -e -o pipefail && \
    curl -fsSL https://download.docker.com/linux/debian/gpg | apt-key add - && \
    echo "deb [arch=$(dpkg --print-architecture)] https://download.docker.com/linux/debian $(. /etc/os-release && echo "$VERSION_CODENAME") stable" > /etc/apt/sources.list.d/docker.list && \
    apt-get update && apt-get install --no-install-recommends -y \
    docker-buildx-plugin \
    docker-ce-cli \
    docker-compose-plugin \
    && rm -rf /var/lib/apt/lists/*

COPY entry.sh /entry.sh
RUN chmod a+rx /entry.sh

ENTRYPOINT [ "/bin/bash" ]
CMD [ "/entry.sh" ]
