# Gunakan base image Node
FROM node:18-alpine

# Set working directory
WORKDIR /app

# Copy package.json dulu
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy semua source code
COPY . .

# Expose port
EXPOSE 3000

# Jalankan aplikasi
CMD ["npm", "start"]