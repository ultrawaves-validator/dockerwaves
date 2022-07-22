FROM node:18-alpine

RUN apk add --no-cache build-base git python3

WORKDIR /opt
RUN git clone -b v2.1.0 --depth 1 https://github.com/eco-stake/restake

WORKDIR /opt/restake
RUN npm ci
RUN echo '{"umee":{"enabled":true,"prettyName":"umee","authzSupport": true, "restUrl":"https://rest.cosmos.directory/umee","rpcUrl":"https://rpc.cosmos.directory/umee","operators":[{"address":"umeevaloper15kddnzxnl24lxddjcmn5m6t2xkmn6uhltqjlgx","restake":{"address":"umee1jhu62l4s6ef4nv7vasad6gqzf3r7hrw9zg3320","run_time":"every 5 minutes","minimum_reward":1}}]}}' > src/networks.local.json

ENTRYPOINT ["npm", "run", "autostake"]
