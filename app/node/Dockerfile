FROM node:10.15.3-alpine

WORKDIR /usr/src/app

COPY package*.json ./

RUN npm ci

COPY ./ ./

ENV PORT 8080

EXPOSE $PORT

USER node

CMD [ "npm", "start"]
