FROM ubuntu:18.04

WORKDIR /home/jenkins

COPY agent.jar .

# hadolint ignore=DL3008
RUN apt-get update -y \
    && apt-get install --no-install-recommends curl openjdk-11-jdk git maven -y \
    && adduser --disabled-password --gecos "" jenkins \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN curl -fsSL https://get.docker.com/ | sh