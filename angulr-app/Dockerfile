FROM node:16.19.1-alpine3.17
RUN npm i -g @angular/cli@14



# Set up app user and group
RUN addgroup app && adduser -S -G app admin

# Set the working directory to /app
WORKDIR /app

# Set the ownership and permissions of the /app directory and its contents
RUN chown -R admin:app /app && chmod -R 770 /app

# Switch to the admin user
USER admin

# Copy the package.json and package-lock.json files and install dependencies
COPY --chown=admin:app package*.json ./
RUN npm install

# Copy the rest of the application code into the container
COPY --chown=admin:app . .

ENV API_PATH=http://api.localhost
EXPOSE 4200

# CMD ["npm", "start"]
ENTRYPOINT ["ng", "s","--host","0.0.0.0","--disable-host-check"]