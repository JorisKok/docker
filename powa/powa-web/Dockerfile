#vim:set ft=dockerfile
FROM debian:jessie
MAINTAINER Julien Rouhaud <julien.rouhaud@dalibo.com>

WORKDIR /usr/local/src

RUN apt-get update && apt-get install -y \
    libpq5 \
    libpq-dev \
    python \
    python-dev \
    python-pip \
    python-tornado \
    && pip install --upgrade pip \
    && pip install --upgrade setuptools \
    && pip install powa-web==3.2.0 \
    && apt-get purge -y --auto-remove libpq-dev python3-dev python3-pip \
    && rm -rf /var/lib/apt/lists/*

COPY powa-web.conf /etc/

EXPOSE 8888
CMD ["powa-web"]
