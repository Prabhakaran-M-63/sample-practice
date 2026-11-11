# 1. Use the lightweight Alpine Linux base image instead of node:latest
FROM node:22-alpine

WORKDIR /app

# 2. Copy package files first to leverage Docker layer caching
COPY package*.json ./

# 3. Install only production dependencies and clean the npm cache
RUN npm install --omit=dev && npm cache clean --force

# 4. Copy the rest of your application code
COPY . .

EXPOSE 8080
ENTRYPOINT ["node"]
CMD ["server.js", "development"]

