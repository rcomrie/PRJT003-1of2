# Dockerized Web Application Deployment on Amazon Linux EC2
Project Overview
This project focuses on containerizing a web application and deploying it on an Amazon Linux EC2 instance using Docker. The workflow includes setting up the EC2 instance, installing required dependencies, creating a Docker image from source code, deploying the containerized application, and pushing the image to Docker Hub for version control and future scalability.

Technical Implementation
Key Steps:
Provision EC2 Instance:

Launch an Amazon Linux EC2 instance and install Docker and Git.
Source Code Acquisition:
Clone the application repository from GitHub into a designated working directory.



Containerization:
Create a Dockerfile to define the containerized environment.
Build a Docker image from the raw source code.
Deployment & Configuration:

Run the Docker container, exposing it on a specified port.
Configure AWS Security Groups to allow traffic to the application.
Image Distribution:

Push the Docker image to Docker Hub for centralized storage and future deployments.
Step-by-Step Implementation
Step 1: Launch Amazon Linux EC2 Instance & Install Dependencies
Provision an Amazon Linux EC2 instance and install required packages:

bash
Copy
Edit
sudo yum update -y
sudo yum install -y git docker
sudo systemctl start docker
sudo usermod -aG docker ec2-user
Step 2: Clone Source Code from GitHub
Create a working directory and pull the application source code:

bash
Copy
Edit
mkdir ~/webapp && cd ~/webapp
git clone <repository-url> .
Step 3: Create a Dockerfile
Define the Docker configuration:

bash
Copy
Edit
vi Dockerfile
Add the following content:

dockerfile
Copy
Edit
FROM nginx:alpine
COPY . /usr/share/nginx/html/
Step 4: Build the Docker Image
Execute the following command to generate the Docker image:

bash
Copy
Edit
docker build -t webapp1of2 .
Step 5: Deploy the Container
Run the containerized application and expose it on port 8080:

bash
Copy
Edit
docker run -d -p 8080:80 webapp1of2
Ensure that the AWS Security Group allows inbound traffic on port 8080.

Step 6: Push the Image to Docker Hub
Authenticate with Docker Hub and push the image for future deployments:

bash
Copy
Edit
docker login
docker tag webapp1of2 <dockerhub-username>/webapp1of2:latest
docker push <dockerhub-username>/webapp1of2:latest

step-7

docker login
docker tag images:latest repository name
docker images
docker push image name

------------------------------------------------


git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/tassdaq/Docker-App.git
git push -u origin main




