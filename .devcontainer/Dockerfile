FROM python:3.11-slim

ENV DEBIAN_FRONTEND=noninteractive

# Install system dependencies: git, curl, ca-certificates for package management
RUN apt-get update \
  && apt-get install -y --no-install-recommends \
     git \
     curl \
     ca-certificates \
     gnupg \
     build-essential \
  && rm -rf /var/lib/apt/lists/*

# Install UV package manager
RUN curl -LsSf https://astral.sh/uv/install.sh | sh

# Ensure UV is in PATH
ENV PATH="/root/.cargo/bin:$PATH"

# Create non-root user for dev container
ARG USERNAME=vscode
ARG USER_UID=1000
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
  && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
  && apt-get update \
  && apt-get install -y --no-install-recommends sudo \
  && echo "$USERNAME ALL=(ALL) NOPASSWD:ALL" > /etc/sudoers.d/$USERNAME \
  && chmod 0440 /etc/sudoers.d/$USERNAME \
  && rm -rf /var/lib/apt/lists/*

# Set up UV for non-root user
USER $USERNAME
WORKDIR /workspace

# Initialize UV for the user
RUN /root/.cargo/bin/uv --version

SHELL ["/bin/bash", "-c"]
