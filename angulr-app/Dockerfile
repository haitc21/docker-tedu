FROM node:16.19.1-alpine3.17
# RUN addgroup app && adduser -S -G app admin
# USER admin
WORKDIR /app
COPY package*.json .
RUN npm install
COPY . .
ENV API_PATH=http://api.localhost
EXPOSE 4200

# CMD ["npm", "start"]
ENTRYPOINT ["npm", "start"]