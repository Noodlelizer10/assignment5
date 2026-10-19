# Stage 1: Build the production application
FROM node:18-alpine

# Set the working directory inside the container
WORKDIR /app

# Copy package.json and package-lock.json files
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy all the application files
COPY . .

# Build the production application
RUN npm run build

# Stage 2: Serve the built files using Nginx
FROM nginx:stable-alpine

# Copy the built assets from the first stage (index 0) to Nginx's HTML folder
COPY --from=0 /app/dist /usr/share/nginx/html

# Expose port 80 (nginx default port)
EXPOSE 80

# Start nginx to serve the application
CMD ["nginx", "-g", "daemon off;"]
