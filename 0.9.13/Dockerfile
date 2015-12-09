FROM debian:jessie

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

ENV AZURE_CLI_VERSION 0.9.13

RUN apt-get update -qq && \
    apt-get install -qqy --no-install-recommends\
      apt-transport-https \
      build-essential \
      curl \
      ca-certificates \
      git \
      lsb-release \
      python-all \
      rlwrap \
      vim \
      nano \
      jq && \
    rm -rf /var/lib/apt/lists/* && \
    curl https://deb.nodesource.com/node_0.12/pool/main/n/nodejs/nodejs_0.12.4-1nodesource1~jessie1_amd64.deb > node.deb && \
      dpkg -i node.deb && \
      rm node.deb && \
      npm install --global azure-cli@$AZURE_CLI_VERSION && \
      azure --completion >> ~/azure.completion.sh && \
      echo 'source ~/azure.completion.sh' >> ~/.bashrc && \
      azure

ENV EDITOR vim
