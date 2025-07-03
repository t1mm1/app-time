# Dockerfile for app from example. 
# This is frontend path and it has separated Dockerfile.

# Make image from node.
FROM node:alpine

# Set work directory for app.
WORKDIR /app

# Set port for app in the container (that will be created from image).
# It does not make any metter which port be here, because container will use internal tools to set port value.
# It needs just to understand which port be available in the container by default.
EXPOSE 3000

# Copy dependencies.
# In this case it will be package.json and package-lock.json.
COPY package*.json ./

# Install npm.
RUN npm install

# Copy files of app into image app's work directory.
COPY . ./

# Run 'npm run dev'.
# It will run app in dev mode.
# For release use 'start' instead of 'run'.
CMD ["npm", "run", "dev"]