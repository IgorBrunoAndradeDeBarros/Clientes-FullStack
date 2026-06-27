FROM node:18-alpine AS build
WORKDIR /app

RUN npm install -g npm@10

COPY package.json package-lock.json ./
RUN npm ci

COPY . .

ENV NODE_OPTIONS=--openssl-legacy-provider
RUN npm run build -- --configuration production

FROM nginx:alpine

COPY --from=build /app/dist/clientes-app /usr/share/nginx/html
COPY nginx.conf /etc/nginx/conf.d/default.conf

EXPOSE 80
