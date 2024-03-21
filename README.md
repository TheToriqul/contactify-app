# Contactify App (Dockerized React Frontend and Python API Backend)

Contactify is a full-stack email contact management application containerized using Docker. It consists of a React frontend application for the user interface and a Python Flask API for the backend functionality. The project demonstrates connectivity between the frontend and backend applications within Docker containers.

## Overview 

This project demonstrates how to containerize a React frontend application and a Python API backend application using Docker. It also shows connectivity between the two applications within Docker containers.

## Frontend Application (React)

The frontend application is built using React and fetches data from the Python API. It is containerized using Docker and served using an Nginx server.

### Instructions:

1. Navigate to the `frontend` directory.
2. Run `docker build -t frontend .` to build the frontend Docker image.
3. Run `docker run -p 3000:80 frontend` to start the frontend container.
4. Access the frontend application at `http://localhost:3000`.

## Backend Application (Python API)

The backend application is a simple Python API built with Flask. It serves data to the frontend application and is containerized using Docker.

### Instructions:

1. Navigate to the `backend` directory.
2. Run `docker build -t backend .` to build the backend Docker image.
3. Run `docker run -p 5000:5000 backend` to start the backend container.

## Connectivity Between Frontend and Backend

Docker Compose is used to demonstrate connectivity between the frontend and backend applications.

### Instructions:

1. Run `docker-compose up --build` to build and start both the frontend and backend containers.
2. Access the frontend application at `http://localhost:3000`.
3. The frontend application will fetch data from the backend API at `http://localhost:5000`.

## Optional: Implement Reverse Proxy

You can add a reverse proxy like Nginx or Traefik to act as a gateway between the frontend and backend applications.

### Instructions:

1. Configure the reverse proxy to route requests to the appropriate backend services.
2. Update the Docker Compose configuration to include the reverse proxy service.
3. Run `docker-compose up --build` to start all services, including the reverse proxy.

## Conclusion

By following the instructions provided in this README, you can containerize both the React frontend and Python API backend applications using Docker. Additionally, you can demonstrate connectivity between the two applications within Docker containers. Optionally, you can implement a reverse proxy for enhanced functionality and security.

Feel free to reach out if you have any questions or need further assistance! 🚀