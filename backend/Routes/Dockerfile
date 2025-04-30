# Use a Python base image with TensorFlow support
FROM python:3.8-slim

# Set the working directory inside the container
WORKDIR /app

# Copy the requirements.txt file to the container
COPY requirements.txt .

# Install Python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the Python files and models into the container
COPY . .

# Expose a port for the service (if you plan to run it as an HTTP service)
EXPOSE 5001

# Define the default command to run the plagiarism check script
CMD ["python", "plagiarism_check.py"]