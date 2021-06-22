FROM node:16.3.0-alpine

RUN mkdir -p /home/node/app/node_modules && chown -R node:node /home/node/app

WORKDIR /home/node/app

COPY package*.json ./

USER node

RUN npm ci

COPY --chown=node:node . .

EXPOSE 4200/tcp

CMD ["npm", "start", "--", "--host", "0.0.0.0"]
