FROM node:6-alpine@sha256:17258206fc9256633c7100006b1cfdf25b129b6a40b8e5d37c175026482c84e3

EXPOSE 3000

RUN apk add --no-cache tini

WORKDIR /usr/src/app

COPY package.json package.json

RUN npm install && npm cache clean --force

COPY . .

CMD [ "/sbin/tini", "--", "node", "./bin/www" ]
