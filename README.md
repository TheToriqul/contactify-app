# Contactify App (Dockerized React Frontend and Python API Backend)

Contactify is a full-stack email contact management application containerized using Docker. It consists of a React frontend application for the user interface and a Python Flask API for the backend functionality. The project demonstrates connectivity between the frontend and backend applications within Docker containers.

## Overview 

This project demonstrates how to containerize a React frontend application and a Python API backend application using Docker. It also shows connectivity between the two applications within Docker containers.
<figure > 
<p align="center">
  <img src="./system_design.png" alt="project architecture" />
  <p align="center">Project Architecture</p> 
</p>
</figure>

## Frontend Application (React)

The frontend application is built using React and fetches data from the Python API. It is containerized using Docker and served using an Nginx server.

## Backend Application (Python API)

The backend application is a simple Python API built with Flask. It serves data to the frontend application and is containerized using Docker.

## Connectivity Between Frontend and Backend

Docker Compose is used to demonstrate connectivity between the frontend and backend applications.

## Implement Reverse Proxy

You can add a reverse proxy like Nginx to act as a gateway between the frontend and backend applications.

## Conclusion

By following the instructions provided in this README, you can containerize both the React frontend and Python API backend applications using Docker. Additionally, you can demonstrate connectivity between the two applications within Docker containers. Optionally, you can implement a reverse proxy for enhanced functionality and security.

Feel free to reach out if you have any questions or need further assistance! 🚀