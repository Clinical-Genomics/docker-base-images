FROM rust:1.67 as builder
WORKDIR /usr/src/d4tools

RUN cargo install d4tools

FROM python:3.8-slim
COPY --from=builder /usr/local/cargo/bin/d4tools /usr/local/bin/d4tools

ENV PATH="/venv/bin:$PATH"

# Install virtualenv
RUN pip install virtualenv
RUN virtualenv --seeder pip /venv
