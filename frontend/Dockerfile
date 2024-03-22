# Dockerfile for React frontend

# Using nodejs image as starting point
FROM node:alpine AS builder

# Setting working directory
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package.json package-lock.json ./

# Copying rest of the file in image's working directory
COPY . .

# Building the assets
RUN npm install

RUN npm run build

EXPOSE 5173

# Command to run the React app
CMD ["npm", "run", "dev"]
