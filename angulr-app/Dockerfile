FROM node:16.19.1-alpine3.17
RUN npm i -g @angular/cli@14
WORKDIR /app
RUN mkdir data
COPY package*.json .
RUN npm install
COPY . .
ENV API_PATH=http://api.localhost
EXPOSE 4200

# CMD ["npm", "start"]
ENTRYPOINT ["ng", "s","--host","0.0.0.0","--disable-host-check"]