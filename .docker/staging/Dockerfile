FROM node:latest as build-stage
WORKDIR /api-docs
COPY ../.. /api-docs/

FROM nginx as production-stage
RUN mkdir /api-docs
COPY --from=build-stage /api-docs /api-docs
COPY .docker/staging/nginx.conf /etc/nginx/nginx.conf
