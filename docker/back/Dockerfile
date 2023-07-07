FROM node:18

WORKDIR /usr/src/backend/com
COPY ./com .
RUN ls

WORKDIR /usr/src/backend/api
COPY ./api/package*.json ./
RUN cd ./ && npm install
COPY ./api/ .
RUN ls

EXPOSE 4321
CMD [ "node", "index.js" ]