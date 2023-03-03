FROM node:16.14.0-slim as build 
#build multi states, varias fases, pouca mt espaço e acelera processo de build

ARG REACT_APP_BACKEND_URL
ENV REACT_APP_BACKEND_URL $ {REACT_APP_BACKEND_URL}

WORKDIR /app

COPY package.json .
COPY package-lock.json .

RUN npm install --silent

COPY . .

RUN npm run build

#inicio de outra fase - com estas layers (cada comando é uma layer)
FROM nginx:alpine-slim

COPY --from=build /app/build /usr/share/nginx/html