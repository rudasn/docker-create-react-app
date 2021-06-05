FROM node:14.7.0-buster-slim

RUN apt-get update \
  && apt-get install -y python build-essential --no-install-recommends \
  && rm -rf /var/lib/apt/lists/* /usr/share/doc /usr/share/man \
  && apt-get clean

COPY app/package.json app/*yarn* ./app/

WORKDIR /app

RUN yarn install

ARG NODE_ENV="production"
ENV NODE_ENV="${NODE_ENV}" \
    PATH="${PATH}:/node_modules/.bin"

# Last thing, add volumes
# otherwise container /app/node_modules will be overriden
# by whatever is in host /app/node_modules (empty)
# when /app:/app is mounted in docker-compose
VOLUME /app/node_modules
