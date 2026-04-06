FROM node:18-alpine

WORKDIR /app

# Install dependencies first (use package.json only for cache efficiency)
COPY package*.json ./
RUN npm install

# Copy rest of application code
COPY . .

EXPOSE 3000

CMD ["node", "server.js"]
