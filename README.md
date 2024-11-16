# Hosting a Website with Docker Using Apache (httpd) 

This project demonstrates how to containerize and host a simple website using Docker. We will create a Docker image that runs an Apache HTTP server (httpd) and serves a static website. The resulting container can be easily deployed on any machine with Docker installed.

**Features**

**Dockerized: The website is packaged and deployed within a Docker container.**

**Web Server: Apache HTTP server (httpd) is used to serve the website's static files.**

**Portability: The website can be deployed to any platform that supports Docker, such as AWS EC2, Azure, or a local machine.**

Prerequisites

Before starting, ensure you have the following installed on your machine:

**Docker**

**Git**

Getting Started

**1. Clone the Repository**

Clone the repository to your local machine:

```git clone https://github.com/yourusername/your-repository.git```  
```cd your-repository```
  
**2. Create the Dockerfile**

Navigate into your project directory (if not already there):

```cd <your-project-directory>```

Create a Dockerfile in this directory:


```nano Dockerfile```

Add the following content to your Dockerfile:

dockerfile
# Use the official Apache HTTP server image as the base  
FROM httpd:2.4  

# Copy the static website files into the Apache document root  
COPY . /usr/local/apache2/htdocs/  

# Expose port 80 for the web server  
EXPOSE 80

Save and exit:

```Press Ctrl + X, then Y to confirm, and hit Enter.```

**3. Build the Docker Image**
Build the Docker image using the Dockerfile:

```docker build -t website-image .```

**4. Run the Docker Container**
Run the container to serve the website:

```docker run -d -p 8080:80 website-image``` 

This command maps port 8080 on your host machine to port 80 inside the container, which is the default HTTP port for Apache.

**5. Access the Website**
Once the container is running, access the website by navigating to:

```Locally: http://localhost:8080```

On a remote server (e.g., AWS EC2): Replace localhost with your server's public IP:

```http://<your-server-ip>:8080```


**Conclusion
This project demonstrates how to host a static website using Docker and Apache HTTP server. You can easily customize and extend the website content within the repository for your needs.**

Feel free to contribute or open issues if you encounter any problems!

License
This project is licensed under the MIT License.
