FROM debian:jessie
MAINTAINER Tibo Delor "delor.thibault@gmail.com"

ARG BUILD_DATE
ARG VCS_REF
LABEL org.label-schema.build-date=$BUILD_DATE \
    org.label-schema.docker.dockerfile="/Dockerfile" \
    org.label-schema.license="MIT" \
    org.label-schema.name="Docker Rust" \
    org.label-schema.url="https://hub.docker.com/r/thibaultdelor/docker-rust" \
    org.label-schema.vcs-ref=$VCS_REF \
    org.label-schema.vcs-type="Git" \
    org.label-schema.vcs-url="https://github.com/thibaultdelor/docker-rust"
    
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install  --no-install-recommends -qqy curl ca-certificates build-essential \
    && rm -rf /var/lib/apt/lists/* \
    && curl -sSkLO https://static.rust-lang.org/dist/rust-1.10.0-x86_64-unknown-linux-gnu.tar.gz \
    && curl -sSkL https://static.rust-lang.org/dist/rust-1.10.0-x86_64-unknown-linux-gnu.tar.gz.sha256 | sha256sum -c - \
    && mkdir rust \
    && tar -C /rust -xzf rust-1.10.0-x86_64-unknown-linux-gnu.tar.gz --strip-components=1 \
    && /rust/install.sh --without=rust-docs \
    && rm -rf /rust-1.10.0-x86_64-unknown-linux-gnu.tar.gz /rust /usr/local/share/doc/ /usr/local/share/man/
