FROM debian:jessie
MAINTAINER Tibo Delor "delor.thibault@gmail.com"

RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install  --no-install-recommends -qqy curl \
    && rm -rf /var/lib/apt/lists/* \
    && curl -sSkLO https://static.rust-lang.org/dist/rust-1.11.0-x86_64-unknown-linux-gnu.tar.gz \
    && curl -sSkL https://static.rust-lang.org/dist/rust-1.11.0-x86_64-unknown-linux-gnu.tar.gz.sha256 | sha256sum -c - \
    && mkdir rust \
    && tar -C /rust -xzf rust-1.11.0-x86_64-unknown-linux-gnu.tar.gz --strip-components=1 \
    && /rust/install.sh --without=rust-docs \
    && rm -rf /rust-1.10.0-x86_64-unknown-linux-gnu.tar.gz /rust /usr/local/share/doc/ /usr/local/share/man/
