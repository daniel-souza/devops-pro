FROM node:18-alpine3.16

WORKDIR /app

COPY ./src .
RUN npm install
EXPOSE 8080
CMD [ "node", "server.js" ]