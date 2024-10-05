FROM node:18-alpine as builder
WORKDIR /usr/app
COPY ./package.json ./
RUN npm install
COPY ./ ./
RUN npm run builder


FROM node:18-alpine
WORKDIR /usr/appCOPY ./package.json ./
RUN npm install
COPY --from=builder /usr/app/dist /usr/appCOPY ./package.json ./
CMD ["node", "server.js"]