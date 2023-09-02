FROM node:18.17.1-alpine AS build
WORKDIR /home/node/app
COPY . .
RUN npm install
RUN npm run build

FROM nginx:1.25-alpine
COPY nginx.conf /etc/nginx/nginx.conf
COPY --from=build /home/node/app/dist/desafio /usr/share/nginx/html