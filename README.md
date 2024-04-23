# Rename Your Hostname 
```
sudo hostnamectl set-hostname myapp

/bin/bash
```

# For Docker Installation
```
sudo apt-get update

sudo apt-get install docker.io -y
```
```
sudo usermod -aG docker $USER && newgrp docker
```

# Clone the source code

The first step is to clone the source code for the app. You can do this by using this command :
```
git clone https://github.com/Pradyumna018/MultiPort-Docker-Deployment.git
```
# Change Directory
```
cd CafeApp
```
# Containerize the Application using Docker

Write a Dockerfile with the following code:
```
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

```

# Now Build Docker Image
```
docker build -t my-web-app .
```

# After building the image, you can run a container using the following command:
```
docker run -p 8080:80 my-web-app
```
# Now go to your instance and add one port in security group  which is 8080
Now try with your public ip : *<public_ip>:8080*

# Follow the same process in Wedding app. But when you are creating another container instead of 8080, use different port.


