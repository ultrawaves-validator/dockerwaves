FROM node:18-alpine

RUN apk add --no-cache build-base git python3

WORKDIR /opt
RUN git clone -b v2.1.0 --depth 1 https://github.com/eco-stake/restake

WORKDIR /opt/restake
RUN npm ci

ENTRYPOINT ["sh", "-c", "echo -n $LOCAL_NETWORKS_BASE64 | base64 -d > src/networks.local.json && npm run autostake umee"]
