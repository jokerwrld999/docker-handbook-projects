FROM node:lts-alpine as builder

WORKDIR /opt/app

COPY ./package.json .
RUN npm install

COPY . .
RUN npm run build

FROM nginx:stable-alpine

EXPOSE 80

COPY --from=builder /opt/app/dist /usr/share/nginx/html