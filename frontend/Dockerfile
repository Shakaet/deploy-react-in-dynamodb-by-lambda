# Use lightweight Node base image
FROM node:22-slim

# Set working directory
WORKDIR /app

# Copy only package.json and package-lock.json first
# This allows Docker to cache npm install if package.json hasn't changed
COPY package*.json ./

# Install dependencies (production optional: --production)
RUN npm install

# Copy the rest of the project files
COPY . .

# Expose the dev port
EXPOSE 5173

# Start the app
CMD ["npm", "run", "dev", "--", "--host", "0.0.0.0"]