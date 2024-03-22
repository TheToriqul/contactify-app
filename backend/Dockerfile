# Dockerfile for Python API backend

# Use Python image as the base
FROM python:alpine

# Set the working directory in the container
WORKDIR /app

# Copy the Python requirements file to the container
COPY requirements.txt .

# Install Python dependencies
RUN pip install -r requirements.txt

# Copy the rest of the application code to the container
COPY . .

# Expose port 5000
EXPOSE 5000

# Command to run the Python app
CMD ["python", "main.py"]
