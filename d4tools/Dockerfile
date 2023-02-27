###########
# BUILDER #
###########

FROM rust:latest AS builder

RUN cargo install d4tools

#########
# FINAL #
#########

FROM debian:bullseye-slim

# Import lib from builder
COPY --from=builder /usr/local/cargo/bin/d4tools /usr/local/bin/d4tools

CMD ["d4tools"]
