# Use a base image with Python and Alpine Linux
FROM python:3.9-alpine

# Set the working directory in the container
WORKDIR /app

# Copy the Python requirements file into the container
COPY requirements.txt requirements.txt

# Install any needed packages specified in requirements.txt
RUN pip install --no-cache-dir -r requirements.txt

# Copy the application code into the container
COPY main.py main.py

# Copy .env.example to .env (Assuming .env.example is in the same directory as your Dockerfile)
COPY .env.sample .env

# Expose a port (e.g., 5000) that the Flask app will run on
EXPOSE 5000

# Define the command to run your Flask application
CMD ["flask", "run", "--host=0.0.0.0"]

