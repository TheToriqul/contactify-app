# Contactify App

Contactify is a full-stack email contact management application containerized using Docker. It consists of a React frontend application for the user interface and a Python Flask API for the backend functionality. The project demonstrates connectivity between the frontend and backend applications within Docker containers.

## Features

- **Flask Backend**: Utilizes Flask, a lightweight WSGI web application framework in Python, for building the backend server.
- **React Frontend**: Implements the frontend using React, a JavaScript library for building user interfaces.
- **RESTful API**: Communicates between the frontend and backend using a RESTful API architecture.
- **Authentication**: Provides user authentication functionality for securing routes and managing user sessions.
- **Database Integration**: Supports integration with various databases like SQLite, MySQL, or PostgreSQL for storing application data.
- **Webpack Build**: Utilizes Webpack for bundling frontend assets and optimizing the build process.
- **Responsive Design**: Ensures that the application layout adapts to different screen sizes, providing a consistent user experience across devices.


## Technologies Used

- React: JavaScript library for building user interfaces.
- Flask: Python web framework for building APIs.
- Docker: Containerization platform for packaging applications.
- Axios: Promise-based HTTP client for making requests in the frontend.
- SQLite: Lightweight relational database used for storing contact information.

## Usage

### Prerequisites

- Docker installed on your machine.

### Running the Application

1. Clone the repository:

```bash
git clone https://github.com/TheToriqul/Contactify-App.git
cd Contactify-App
```

2. Build and run the Docker containers using Docker Compose:

```bash
docker-compose up --build
```

3. Access the application in your browser:

- Frontend: [http://localhost](http://localhost)
- Backend API: [http://localhost/api/data](http://localhost/api/data)

## Directory Structure

```
Contactify-App/
  ├── my-react-app/        # React frontend application
  │   ├── Dockerfile       # Dockerfile for frontend
  │   ├── package.json
  │   ├── ...
  │
  ├── my-python-api/       # Python API backend application
  │   ├── Dockerfile       # Dockerfile for backend
  │   ├── requirements.txt # Python dependencies
  │   ├── app.py           # Flask application code
  │   ├── data.db          # SQLite database file
  │   ├── ...
  │
  ├── nginx.conf           # NGINX configuration file for reverse proxy
  ├── docker-compose.yml   # Docker Compose configuration
  └── README.md            # Project README file
```

## Contributing

Contributions are welcome! Feel free to open issues or pull requests for any improvements or new features you'd like to see.
