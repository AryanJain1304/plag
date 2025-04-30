# Base image with Python 3.8 and pip
FROM python:3.8-slim

# Set working directory
WORKDIR /app

# Copy requirements and install Python dependencies
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# Copy the rest of the code (Python scripts, models, etc.)
COPY . .

# Optional: expose a port if you run this as a microservice
EXPOSE 5001

# Default command (you can override this in docker-compose if needed)
CMD ["python", "plagiarism_check.py"]