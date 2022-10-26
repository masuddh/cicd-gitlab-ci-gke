FROM  mhart/alpine-node:6.10

ARG       NODE_ENV=production
ENV       NODE_ENV $NODE_ENV
WORKDIR   /app

COPY      ./service-nodejs /app

EXPOSE    8080
CMD       ["node", "index.js"]
