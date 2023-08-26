FROM node:18-alpine as build

WORKDIR /frontend/com
COPY ./com .
RUN ls

WORKDIR /frontend/app
COPY ./app/package*.json ./
RUN npm install
ENV VITE_API_URL=http://52.47.196.206:80/api
COPY ./staff/flors-rueda/fullstack/project/app/ .
RUN npm run build


FROM nginx:stable-alpine
COPY --from=build /frontend/app/dist /bin/www
COPY ./docker/front/nginx.conf /etc/nginx/conf.d/default.conf
EXPOSE 80
CMD [ "nginx", "-g", "daemon off;" ]