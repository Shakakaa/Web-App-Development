# Use the official Python image as the base image
FROM python:3.9-slim

# Set the working directory in the container
WORKDIR /app

# Copy the requirements file and install dependencies
COPY requirements.txt . 
RUN pip install --no-cache-dir -r requirements.txt

# Copy application code into the container
COPY app.py .

# Set app.py as the entry point for the container
ENTRYPOINT ["python", "app.py"]
