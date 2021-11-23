FROM python:3.8-slim

ENV PATH="/venv/bin:$PATH"

RUN apt-get update && \
    apt-get -y upgrade && \
    apt-get -y install -y --no-install-recommends gcc libc-dev libz-dev

# Install virtualenv
RUN pip install virtualenv
RUN virtualenv --seeder pip /venv

RUN pip install --no-cache-dir "cyvcf2<0.10.0"
