FROM alpine:3.17

WORKDIR /app

COPY package*.json .npmrc /app/

RUN npm install

COPY . .

RUN sed -i -e "s/process.env.\([A-Z_]*\)/\"\$\{\1\}\"/g" /app/src/conf.js

RUN npm run build


# production stage
#FROM nginx:stable-alpine as production-stage
#COPY --from=build-stage /app/dist /usr/share/nginx/html
#COPY nginx/nginx-default.conf /home
#COPY nginx/start.sh /home
#CMD ["/bin/sh", "/home/start.sh"]

