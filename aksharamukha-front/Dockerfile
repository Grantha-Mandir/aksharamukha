# develop stage
FROM node:14.17-alpine as build-stage

WORKDIR /app

COPY ./aksharamukha-front/. .

RUN npm install -g @quasar/cli

RUN npm install

RUN quasar build

FROM nginx:1.17.5-alpine

COPY --from=build-stage /app/dist/spa-mat /usr/share/nginx/html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]

