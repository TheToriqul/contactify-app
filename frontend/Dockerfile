# Dockerfile for React frontend

# Using nodejs image as starting point
FROM node:alpine AS builder

# Setting working directory
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json /app/

RUN npm ci --only=production

# Copying rest of the file in image's working directory
COPY . .

# Command to run the React app
CMD ["npm", "run", "dev"]