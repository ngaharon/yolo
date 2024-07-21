# Build stage
FROM node:16-alpine3.16 as build-stage

# Set the working directory inside the container
WORKDIR /client

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies and clears the npm cache and removes any temporary files
RUN npm install && \
    npm cache clean --force && \
    rm -rf /tmp/*

# Copy the rest of the application code
COPY . .

# Build the application
RUN npm run build && \
    npm prune --production

# Production stage
FROM node:16-alpine3.16 as production-stage

WORKDIR /client

# Copy only the necessary files from the build stage
COPY --from=build-stage /client/build ./build
COPY --from=build-stage /client/public ./public
COPY --from=build-stage /client/package*.json ./

# Install production dependencies and clean up
RUN npm install --only=production && \
    npm cache clean --force && \
    rm -rf /tmp/*

# Set the environment variable for the app
ENV NODE_ENV=production

# Expose the port used by the app
EXPOSE 27017

# Start the application
CMD ["npm", "start"]
