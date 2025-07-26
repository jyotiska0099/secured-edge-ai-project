# Use a slim Python base image
FROM python:3.9-slim

# Set working directory inside the container
WORKDIR /app

# Copy and install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Default command
CMD [ "/bin/bash" ]
