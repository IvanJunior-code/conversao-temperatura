FROM node:16.15.0 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .

FROM alpine:3.14 as final
RUN apk add --update nodejs npm
WORKDIR /app
COPY --from=build /app .
EXPOSE 8080
CMD ["node", "server.js"]
