FROM python:3.8-slim-bullseye

ENV PATH="/venv/bin:$PATH"

# Install base dependencies
RUN apt-get update && \
     apt-get -y upgrade && \
     apt-get install -y --no-install-recommends wget build-essential gcc zlib1g-dev && \
     apt-get clean && \
     rm -rf /var/lib/apt/lists/*

# Download and install bedtools static binary
RUN cd /usr/local/bin && \
    wget -q https://github.com/arq5x/bedtools2/releases/download/v2.31.1/bedtools.static.binary && \
    mv bedtools.static.binary bedtools && \
    chmod +x bedtools

# Install virtualenv
RUN pip install virtualenv
RUN virtualenv --seeder pip /venv
