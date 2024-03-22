# Dockerfile for Python API backend

# Use Python image as the base
FROM python:alpine

# Set the working directory in the container
WORKDIR /api

# ENV Configurations
# ENV FLASK_APP=main.py
# ENV FLASK_ENV=development 

# Copy the Python requirements file to the container
COPY ./requirements.txt /api/requirements.txt

# Install Python dependencies
RUN pip install --no-cache-dir --upgrade -r /api/requirements.txt

# Copy the rest of the application code to the container
COPY . /api/

# Expose port 5000
# EXPOSE 5000

# Command to run the Python app
CMD ["python", "main.py", "--host", "0.0.0.0", "--port", "5000"]
