FROM python:3.8-slim

RUN apt-get update && \
    apt-get install -y curl

WORKDIR /tmp

RUN curl https://sh.rustup.rs -sSf > rustup.sh
RUN chmod 755 rustup.sh
RUN ./rustup.sh -y
RUN rm /tmp/rustup.sh

ENV PATH="/venv/bin:$PATH"

# Install virtualenv
RUN pip install virtualenv
RUN virtualenv --seeder pip /venv
