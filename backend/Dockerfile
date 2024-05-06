# stage 1
FROM node:21 AS backend-build

WORKDIR /app

COPY . .

RUN npm i

# stage 2
FROM node:21-slim

WORKDIR /app

#COPY above stage as compress

COPY --from=backend-build /app .

COPY .env.sample .env

EXPOSE 5000

CMD ["npm","start"]
