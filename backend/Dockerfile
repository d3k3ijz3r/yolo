FROM node:13.12.0-slim

WORKDIR /app

COPY ./package*.json /app/

RUN npm install

COPY . . 

EXPOSE 4000

CMD ["node","server.js"]