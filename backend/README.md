# Contactify - Backend using Python API

This Dockerfile is designed to containerize a Flask application that provides a simple API for managing contacts. Below is a brief explanation of the Dockerfile and the application it encapsulates.

## Dockerfile Explanation:

```dockerfile
FROM python:alpine
```
- This line specifies the base image to build upon, which is `python:alpine`, a lightweight Python image based on Alpine Linux.

```dockerfile
WORKDIR /app
```
- Sets the working directory inside the container to `/app`, where the application code will be copied.

```dockerfile
COPY requirements.txt .
```
- Copies the `requirements.txt` file from the host to the `/app` directory in the container.

```dockerfile
RUN pip install -r requirements.txt
```
- Installs the Python dependencies listed in `requirements.txt` using `pip`.

```dockerfile
COPY . .
```
- Copies the entire current directory (presumably containing the Flask application code) into the `/app` directory of the container.

```dockerfile
EXPOSE 5000
```
- Exposes port 5000 on the container, where the Flask application will be running.

```dockerfile
CMD ["flask", "run", "--host=0.0.0.0", "--port=5000"]
```
- Specifies the default command to run when the container starts. It runs the Flask application with `flask run`, making it accessible on `0.0.0.0:5000`.

## Application Explanation:

The Flask application provides a simple RESTful API for managing contacts. Below are the main endpoints:

- **GET /**: Returns a "Hello World" message as a test endpoint.

- **GET /contacts**: Retrieves all contacts from the database and returns them as JSON.

- **POST /create_contact**: Creates a new contact by accepting JSON data with keys `firstName`, `lastName`, and `email`. If successful, returns a success message.

- **PATCH /update_contact/<int:user_id>**: Updates an existing contact specified by `user_id` with JSON data containing fields to update. If successful, returns a success message.

- **DELETE /delete_contact/<int:user_id>**: Deletes an existing contact specified by `user_id`. If successful, returns a success message.

The application assumes the existence of a database configured through `config.py` and utilizes `models.py` for defining the Contact model.

## How to Use:

### Locally:
To run the Flask application locally without Docker, ensure you have Python and pip installed on your system. Then follow these steps:

1. **Install Dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

2. **Run the Application:**
   ```bash
   flask run
   ```

3. **Access the Application:**
   Open a web browser and navigate to `http://localhost:5000` to access the Flask application.

### Using Docker:
To build the Docker image, navigate to the directory containing this Dockerfile and run the following command:

```bash
docker build -t <image_name> .
```

Replace `<image_name>` with the desired name for your Docker image.

Once the image is built, you can run a container using the following command:

```bash
docker run -p 5000:5000 <image_name>
```

This will start the Flask application within a Docker container, and you can access it by navigating to `http://localhost:5000` in your web browser.

### Notes:
- Ensure that your Flask application code is compatible with Python 3 and adheres to standard Flask application structure.
- Customize the Dockerfile as needed to accommodate additional dependencies or specific requirements of your application.
- Always follow best practices for Dockerfile creation and container security.
- Remember to replace placeholders such as `<image_name>` with actual values relevant to your project.

Feel free to adjust the Dockerfile or Flask application according to your needs. For more detailed information on using Flask, refer to the [Flask documentation](https://flask.palletsprojects.com/).
