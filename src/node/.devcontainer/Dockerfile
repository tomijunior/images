ARG VARIANT=alpine-3.22
FROM mcr.microsoft.com/devcontainers/base:${VARIANT}

ARG NODE_PACKAGE_VERSION=24.7.0

WORKDIR /opt
RUN apk update \
    && wget https://unofficial-builds.nodejs.org/download/release/v${NODE_PACKAGE_VERSION}/node-v${NODE_PACKAGE_VERSION}-linux-x64-musl.tar.gz \
    && mkdir -p /opt/nodejs \
    && tar -zxvf *.tar.gz --directory /opt/nodejs --strip-components=1 \
    && rm *.tar.gz \
    && ln -s /opt/nodejs/bin/node /usr/local/bin/node \
    && ln -s /opt/nodejs/bin/npm /usr/local/bin/npm \
    && ln -s /opt/nodejs/bin/npx /usr/local/bin/npx \
    && apk --no-cache add yarn \
    && npm install --global eslint 

ENV PATH="/opt/nodejs/bin:$PATH"