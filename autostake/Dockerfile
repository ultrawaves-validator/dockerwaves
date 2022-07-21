FROM node:18-alpine

RUN apk add --no-cache build-base git python3

WORKDIR /opt
RUN git clone -b v2.1.0 --depth 1 https://github.com/eco-stake/restake

WORKDIR /opt/restake
RUN npm ci
RUN echo '{"umee": {"enabled": true}}' > src/networks.local.json

ENTRYPOINT ["npm", "run", "autostake"]
