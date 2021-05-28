FROM node:lts-alpine as build



# install simple http server for serving static content
RUN npm install -g http-server

# make the 'app' folder the current working directory
WORKDIR /app

# copy both 'package.json' and 'package-lock.json' (if available)
COPY package*.json ./

# install project dependencies
RUN npm install

# copy project files and folders to the current working directory (i.e. 'app' folder)
COPY . .
# build app for production with minification
RUN npm run build

FROM nginx:1.19.0-alpine AS prod-stage

COPY --from=build /and/aksharamukha-front /usr/share/nginx/html

EXPOSE 8085
# CMD [ "http-server", "dist" ]

CMD ['nginx',"-g", "daemon off;"]