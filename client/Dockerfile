# Use a specific Node.js version
FROM node:13.12.0-slim AS build

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json for dependency installation
COPY package*.json /app/

# Install dependencies
RUN npm install --silent

# Install react-scripts globally
RUN npm install -g react-scripts --silent

# Copy the application code
COPY . .

# Build the application
RUN npx react-scripts build

# Use the official Nginx image for serving the application
FROM nginx:latest

# Expose port 80
EXPOSE 80

# Copy the built application from the 'build' stage to the Nginx document root
COPY --from=build /app/build/ /var/www/html

# Copy Nginx configuration
COPY ./nginx/default.conf /etc/nginx/conf.d/

# Start Nginx in the foreground
CMD ["nginx", "-g", "daemon off;"]
