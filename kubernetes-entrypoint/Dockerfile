FROM ubuntu:16.04

MAINTAINER Pete Birley <pete@port.direct>

ARG VERSION=v0.1.0

ENV DEBIAN_FRONTEND=noninteractive

RUN set -x \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
    && curl -L https://github.com/stackanetes/kubernetes-entrypoint/releases/download/${VERSION}/kubernetes-entrypoint > /usr/bin/kubernetes-entrypoint \
    && chmod +x /usr/bin/kubernetes-entrypoint \
    && apt-get purge -y --auto-remove \
        ca-certificates \
        curl \
    && rm -rf /var/lib/apt/lists/*


ENTRYPOINT ["/usr/bin/kubernetes-entrypoint"]
