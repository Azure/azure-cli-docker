FROM node:6-slim

RUN rm /bin/sh && ln -s /bin/bash /bin/sh

ENV AZURE_CLI_VERSION="0.10.18" \
    EDITOR=vim

RUN apt-get update -qq && \
    apt-get install -qqy --no-install-recommends \
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
      jq

#Run as non-root node user
WORKDIR /home/node/
RUN mkdir -p /home/node/app /home/node/.npm-global && \
    chown -R node:node /home/node
ENV PATH=/home/node/.npm-global/bin:$PATH \
    NPM_CONFIG_PREFIX=/home/node/.npm-global

USER node
RUN npm install --global azure-cli@${AZURE_CLI_VERSION} && \
    azure --completion >> ~/azure.completion.sh && \
    echo 'source ~/azure.completion.sh' >> ~/.bashrc && \
    azure

RUN azure config mode arm

ENTRYPOINT ["azure"]
