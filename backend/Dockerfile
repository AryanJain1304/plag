# server/Dockerfile
FROM node:18-alpine
RUN apk add --no-cache bash
WORKDIR /app
COPY backend/package.json backend/package-lock.json ./
RUN npm install
COPY backend/ .
EXPOSE 5000
CMD ["node", "server.js"]