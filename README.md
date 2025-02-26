# Dockerized Web Application Deployment on Amazon Linux EC2

## Project Overview
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

![Screenshot 2025-02-23 122016](https://github.com/user-attachments/assets/dd44f7e4-5d99-4321-af0d-a2e54b9022e3)

![Screenshot 2025-02-23 122930](https://github.com/user-attachments/assets/1b680af2-7879-4c0a-8b14-ad33226d2f2f)


Step 2: Clone Source Code from GitHub
Create a working directory and pull the application source code:

bash
Copy
Edit
mkdir ~/webapp1of2 && cd ~/webapp1of2
git clone <repository-url> .


Step 3: Create a Dockerfile
Define the Docker configuration:

vi Dockerfile
FROM nginx:alpine
COPY . /usr/share/nginx/html/

Step 4: Build the Docker Image
Execute the following command to generate the Docker image:

docker build -t webapp1of2 .

![Screenshot 2025-02-23 123243](https://github.com/user-attachments/assets/22109fc6-0d7e-4737-a9be-1471f8c92955)

Step 5: Deploy the Container
Run the containerized application and expose it on port 8080:

![Screenshot 2025-02-23 124539](https://github.com/user-attachments/assets/31816911-f95f-4298-9891-a5ae6880c98e)

docker run -d -p 8080:80 webapp1of2
Ensure that the AWS Security Group allows inbound traffic on port 8080.

![Screenshot 2025-02-23 122252](https://github.com/user-attachments/assets/6e606d9d-558e-4831-aa28-98b72386d92f)

![Screenshot 2025-02-23 124843](https://github.com/user-attachments/assets/6c82570c-5560-4de2-91a5-e39073b97089)

![Screenshot 2025-02-23 124911](https://github.com/user-attachments/assets/370e23ec-e0e9-4087-aeac-89381575215d)


Step 6: Push the Image to Docker Hub
Authenticate with Docker Hub and push the image for future deployments:

docker login
docker tag webapp1of2 <dockerhub-username>/webapp1of2:latest
docker push <dockerhub-username>/webapp1of2:latest

![Screenshot 2025-02-23 125939](https://github.com/user-attachments/assets/61e323fb-864d-492c-8d90-d5bfaac29945)

![Screenshot 2025-02-23 125905](https://github.com/user-attachments/assets/584ff3d2-3efe-4e4d-ac71-029f2304eced)



