FROM    rust:1.24-jessie as builder
COPY    .   /src
WORKDIR /src
RUN     cargo build --release

FROM    debian:jessie-slim
WORKDIR   /root/
COPY  --from=builder /src/target/release/dkjdlkzdzedz app
CMD       ["./app"]