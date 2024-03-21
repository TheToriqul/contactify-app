# Dockerfile for React frontend

# Multi-stage build pipeline

# STAGE 1: Building assets using Node image
# Using nodejs image as starting point
FROM node:alpine AS builder
# Setting working directory
WORKDIR /app

# Copy package.json and package-lock.json to the container
COPY package.json package-lock.json ./

# Copying rest of the file in image's working directory
COPY . .

# set arguements
ARG VITE_API_URL
ENV VITE_API_URL=${VITE_API_URL}

# Building the assets
RUN npm install

RUN npm run build

EXPOSE 3000
# Command to run the Python app
CMD ["npm", "run", "preview"]
