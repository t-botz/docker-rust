FROM thibaultdelor/docker-rust:nightly

RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

CMD cargo run --release

ONBUILD COPY . /usr/src/app
ONBUILD RUN cargo build --release
