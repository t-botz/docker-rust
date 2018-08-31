FROM rustlang/rust:nightly-slim

RUN rustup component add rustfmt-preview clippy-preview

# Install OpenSSL - see https://github.com/sfackler/rust-openssl
RUN apt-get update && \
    apt-get install --no-install-recommends -y pkg-config libssl-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
