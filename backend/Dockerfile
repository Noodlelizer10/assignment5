# Use Node.js 18 alpine base image
FROM node:18-alpine

# Set a working directory inside the container
WORKDIR /usr/src/app

# Copy package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all the application files
COPY . .

# Create a directory for the SQLite database file
RUN mkdir -p /app/data

# Expose port 5000
EXPOSE 5000

# Start the application
CMD ["npm", "start"]
