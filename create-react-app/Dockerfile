FROM node:14.7.0-buster-slim

RUN apt-get update \
  && apt-get install -y python build-essential --no-install-recommends \
  && rm -rf /var/lib/apt/lists/* /usr/share/doc /usr/share/man \
  && apt-get clean

RUN mkdir -p /node_modules && chown node:node -R /node_modules

WORKDIR /

RUN npx create-react-app app

RUN chown node:node /app

WORKDIR /app

COPY overrides/. ./

RUN mv README.md REACT.md
