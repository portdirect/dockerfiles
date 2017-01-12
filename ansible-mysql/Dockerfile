FROM ubuntu:16.04

MAINTAINER Pete Birley <pete@port.direct>

ARG VERSION=2.2.0

ENV DEBIAN_FRONTEND=noninteractive

RUN set -x \
    && apt-get update \
    && apt-get install -y --no-install-recommends \
        build-essential \
        python \
        python-dev \
        libssl-dev \
        ca-certificates \
        libmysqlclient-dev \
        curl \
    && curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py \
    && python get-pip.py \
    && rm get-pip.py \
    && pip install --no-cache \
        ansible==${VERSION} \
        MySQL-python \
    && apt-get purge -y --auto-remove \
        build-essential \
        python-dev \
        libmysqlclient-dev \
        libssl-dev \
        ca-certificates \
        curl \
    && rm -rf /var/lib/apt/lists/* /root/.cache \
    && find / -type f \( -name "*.pyc" -o -name "pip" -o -name "easy_install" -o -name "wheel" \) -delete

ENTRYPOINT ["/usr/local/bin/ansible"]
