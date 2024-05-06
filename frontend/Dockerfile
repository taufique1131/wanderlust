# stage 1
FROM node:21 AS frontend_build

WORKDIR app

#copy package.jason and package.json for dependecy installation
COPY package*.json ./

#install dependecy
RUN npm install

#copy code
COPY . .

#stage 2
FROM node:21-slim

WORKDIR app

# cpy above stage as compressed

COPY --from=frontend_build /app .

COPY .env.sample .env.local

EXPOSE 5173

CMD ["npm","run","dev","--","--host"]
