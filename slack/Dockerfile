# Choose the latest LTS (Long Term Support) version of node as our base image
FROM node:lts@sha256:9aa3de5470c99408fda002dc1f406e92a31daf0492eb33d857d8d9d252edcc52

ARG PROJECT_ROOT="."

# Create a directory for our application
WORKDIR /app

# Copy only the build artifact and package.json into our app directory
COPY ${PROJECT_ROOT}/dist .
COPY ${PROJECT_ROOT}/package .

# Install only production dependencies
RUN npm install --omit=dev --silent

# The application's default port is picked from the environment
EXPOSE $PORT

# Start the application
CMD [ "node", "app.js" ]
