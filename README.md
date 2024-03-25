# Contactify: Containerized React Frontend and Python API Backend with Connectivity

Welcome to my Containerized React Frontend and Python API Backend with Connectivity repository! This project demonstrates the containerization of a React frontend application and a Python API backend application using Docker. The focus here is on containerization using Docker, showcasing connectivity between the two applications.

## Overview

I'm showcasing how I containerize both the React frontend and Python API backend applications using Docker, as well as how to establish connectivity between them.

### Project Architecture

<figure > 
<p align="center">
  <img src="./system_design.png" alt="project architecture" />
  <p align="center">Project Architecture</p> 
</p>
</figure>

**Frontend Application (React):**
- Built using React
- Containerized with Docker
- Served using an Nginx server

**Backend Application (Python API):**
- Simple Python API built with Flask
- Containerized with Docker

### Connectivity Between Frontend and Backend

I utilize Docker Compose to demonstrate connectivity between the frontend and backend applications.

### Implement Reverse Proxy

For enhanced functionality and security, I have implemented a reverse proxy like Nginx to act as a gateway between the frontend and backend applications.

## Instructions

1. Clone my repository:

    ```bash
    git clone https://github.com/TheToriqul/Contactify-App.git
    ```

2. Navigate to the project directory:

    ```bash
    cd Contactify-App
    ```

3. Build and run the Docker containers using Docker Compose:

    ```bash
    docker-compose up --build
    ```

4. Access my Containerized React Frontend and Python API Backend with Connectivity in your browser:

    ```
    http://localhost:3000
    ```

## Dockerfiles

### Backend Dockerfile (./backend/Dockerfile)

My Backend Dockerfile starts with a Python Alpine base image, sets the working directory to `/app`, copies `requirements.txt`, installs Python dependencies, copies the application code, exposes port `5000`, and sets the command to run the Flask application.

### Frontend Dockerfile (./frontend/Dockerfile)

My Frontend Dockerfile sets up a build environment using a Node Alpine base image, sets the working directory to `/app`, copies all files, installs dependencies, and builds the React application. Then, it uses an Nginx Alpine base image, sets the working directory to serve static files, and copies the built files. It exposes port `3000`.

## Conclusion

By following my instructions, you can containerize both the React frontend and Python API backend applications using Docker. Additionally, you can demonstrate connectivity between the two applications within Docker containers. Optionally, you can implement a reverse proxy for enhanced functionality and security.

Feel free to reach out if you have any questions or need further assistance! 🚀
