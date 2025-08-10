# Use official Node LTS image
FROM node:18

# Set working directory
WORKDIR /app

# Install dependencies
COPY package.json package-lock.json ./
RUN npm install

# Install PM2 globally
RUN npm install -g pm2

# Copy remaining app files
COPY . .

# Expose app port (adjust if your server.js uses another)
EXPOSE 80

# Use PM2 to run the app
CMD ["pm2-runtime", "start", "server.js", "--name", "veera"]
