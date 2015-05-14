FROM ubuntu:14.04

RUN apt-get update && \
        apt-get -qqy install --no-install-recommends nodejs-legacy npm && \
        sudo npm install --global azure-cli@0.9.2 && \
        azure
