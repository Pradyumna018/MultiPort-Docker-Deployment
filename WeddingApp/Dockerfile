# Use an existing image as a base
FROM nginx:alpine

# Set the working directory inside the container
WORKDIR /usr/share/nginx/html

# Copy the web application files from the host into the container
COPY . .

# Expose port 80 to the outside world
EXPOSE 80

# Command to run the web server when the container starts
CMD ["nginx", "-g", "daemon off;"]
