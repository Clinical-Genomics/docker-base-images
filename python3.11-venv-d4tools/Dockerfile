###########
# BUILDER #
###########

FROM python:3.11-slim as builder

# Install base dependencies
RUN apt-get update && \
     apt-get -y upgrade && \
     apt-get install -y --no-install-recommends build-essential curl git && \
     apt-get clean && \
     rm -rf /var/lib/apt/lists/*

# Get Rust
RUN curl https://sh.rustup.rs -sSf | sh -s -- -y

# Add .cargo/bin to PATH
ENV PATH="/root/.cargo/bin:${PATH}"

# Create a non-root user to install packages into
RUN groupadd --gid 1000 worker && useradd -g worker --uid 1000 --shell /usr/sbin/nologin --create-home worker

# Install d4tools
RUN cargo install --git https://github.com/38/d4-format.git d4tools --branch master --root /home/worker/libs/d4tools
ENV PATH="/home/worker/libs/d4tools/bin:${PATH}"

ENV PATH="/venv/bin:$PATH"

# Install virtualenv
RUN pip install --no-cache-dir virtualenv
RUN virtualenv --seeder pip /venv

#########
# FINAL #
#########

FROM python:3.11-slim

# Create a non-root user to run commands
RUN groupadd --gid 1000 worker && useradd -g worker --uid 1000 --shell /usr/sbin/nologin --create-home worker

# Copy pre-installed software from builder
COPY --chown=worker:worker --from=builder /venv /venv
COPY --chown=worker:worker --from=builder /home/worker/libs /home/worker/libs

ENV PATH="/venv/bin:$PATH"
ENV PATH="/home/worker/libs/d4tools/bin:${PATH}"

# Run commands as non-root
USER worker