# Pull base image.
FROM ubuntu

MAINTAINER Khalid Mouss <kmouss@microsoft.com>

COPY azure-cli.0.9.0.tar.gz /

# Install packages
RUN \
        apt-get update && \
        apt-get install -y nodejs-legacy && \
        apt-get install -y npm && \
        sudo npm install /azure-cli.0.9.0.tar.gz --global && \
        rm /azure-cli.0.9.0.tar.gz && \
        azure
