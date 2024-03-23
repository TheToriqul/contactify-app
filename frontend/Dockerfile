# Dockerfile for React frontend

# Using nodejs image as starting point
FROM node:alpine AS builder

# Setting working directory
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package*.json /app/

RUN npm i --silent
RUN npm i -g react-scripts@5.0.0

# Copying rest of the file in image's working directory
COPY . ./

# Command to run the React app
CMD ["npm", "run", "dev"]