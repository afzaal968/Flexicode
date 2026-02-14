# Use a modern Node image
FROM node:20-bullseye

# Install compilers and runtimes
RUN apt-get update && apt-get install -y \
    python3 \
    default-jdk \
    g++ \
    gcc \
    mono-complete \
    && rm -rf /var/lib/apt/lists/*

# Set working directory
WORKDIR /app

# Copy dependency files first
COPY package*.json ./
RUN npm install

# Copy rest of the application
COPY . .

# Use Render's dynamic port
EXPOSE 10000

# Start server
CMD ["node", "index.js"]