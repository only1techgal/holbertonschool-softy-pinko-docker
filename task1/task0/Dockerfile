# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Update API package list and upgrade installed packages
RUN apt-get update && apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# Resolve "externally managed" error if present
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install Flask

# Set the working directory to /app
WORKDIR /app

# Copy the api.py script innto the container
COPY ./api.py /app/api.py

# Run the Flask app
CMD ["python3", "api.py"]