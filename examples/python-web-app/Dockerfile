# Use an official Python image as a base
FROM python:3.12-slim
 
# Install system dependencies for creating a virtual environment
RUN apt-get update && apt-get install -y python3-venv python3-pip
 
# Set the working directory inside the container
WORKDIR /app
 
# Copy the requirements file into the container
COPY requirements.txt .
 
# Create a virtual environment inside the container
RUN python3 -m venv /opt/venv
 
# Activate the virtual environment and install dependencies
RUN /opt/venv/bin/pip install -r requirements.txt
 
# Add the virtual environment to the PATH
ENV PATH="/opt/venv/bin:$PATH"
 
# Copy the rest of the application code into the container
COPY . .
 
# Expose port (example for Django)
EXPOSE 8000
 
# Command to run your Django app (or replace with your app's start command)
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]




