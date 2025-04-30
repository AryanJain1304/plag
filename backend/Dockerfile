# base image
FROM node:18-alpine

# Install Python and required packages
RUN apk add --no-cache bash python3 py3-pip

# Set work directory
WORKDIR /app

# Copy and install Node dependencies
COPY backend/package*.json ./
RUN npm install

# Copy backend code
COPY backend/ .

# Install Python requirements
COPY backend/Routes/requirements.txt ./Routes/
RUN pip3 install --no-cache-dir -r Routes/requirements.txt

# Copy Python code and models
COPY backend/Routes/ ./Routes/

# Expose backend port
EXPOSE 5000

# Start Node server
CMD ["node", "server.js"]
