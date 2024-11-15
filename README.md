
# Hosting a Static Website with Docker

This project demonstrates how to containerize and host a simple static website using Docker. We will create a Docker image that runs an Apache HTTP Server to serve the website’s static files. This containerized website can be deployed on any machine with Docker installed, whether locally or in the cloud.

## Features
- **Dockerized**: The website is packaged and deployed within a Docker container.
- **Web Server**: We use Apache HTTP Server to serve the website’s static content.
- **Portability**: The website can be deployed on any platform that supports Docker, such as AWS EC2, Azure, or your local machine.

## Prerequisites
Before starting, ensure that you have the following software installed on your machine:

- **Docker**
- **Git**

---

## Getting Started


# Hosting a Static Website with Docker

This project demonstrates how to containerize and host a simple static website using Docker. We will create a Docker image that runs an Apache HTTP Server to serve the website’s static files. This containerized website can be deployed on any machine with Docker installed, whether locally or in the cloud.

## Features
- **Dockerized**: The website is packaged and deployed within a Docker container.
- **Web Server**: We use Apache HTTP Server to serve the website’s static content.
- **Portability**: The website can be deployed on any platform that supports Docker, such as AWS EC2, Azure, or your local machine.

## Prerequisites
Before starting, ensure that you have the following software installed on your machine:

- **Docker**
- **Git**

---

## Getting Started

### 1. Clone the Repository
To get started, clone the repository to your local machine:

```bash
git clone https://github.com/yourusername/your-repository.git
cd your-repository

2. Create the Dockerfile
Now, create a Dockerfile in your project directory. This file will define the Docker image that runs the Apache HTTP Server and serves your static website.

Navigate into your project directory (if you haven't already):

bash
Copy code
cd <your-project-directory>
Create the Dockerfile using a text editor:

bash
Copy code
nano Dockerfile
Paste the following content into the Dockerfile:

Dockerfile
Copy code
# Use the official Apache HTTP Server image
FROM httpd:alpine

# Copy the static files from your local project directory to the Apache server's directory
COPY ./ /usr/local/apache2/htdocs/

# Expose port 80 for HTTP traffic
EXPOSE 80
Save and exit the text editor:

In nano, press Ctrl + X, then Y to confirm, and hit Enter.
3. Build the Docker Image
Once you have the Dockerfile ready, build the Docker image using the following command:

bash
Copy code
docker build -t website-image .
This will create a Docker image named website-image using the files in the current directory.

4. Run the Docker Container
After the image is built, you can run the container to serve the website. Use the following command to run the container in detached mode and map port 8080 on your host machine to port 80 inside the container (the default HTTP port for Apache):

bash
Copy code
docker run -d -p 8080:80 website-image
5. Access the Website
Once the container is running, you can access the website by navigating to:

Locally:

http
Copy code
http://localhost:8080
On a remote server (e.g., AWS EC2):

Replace localhost with the public IP address of your EC2 instance:

http
Copy code
http://<your-server-ip>:8080
This URL will display the website served by your Docker container.









