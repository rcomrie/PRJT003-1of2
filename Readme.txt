
Project Title:
Docker Container Webapp Project



Project detail:
The Docker Container Project focuses on deploying a web application using Docker containers on an Amazon Linux EC2 instance. 
The project involves setting up an EC2 instance, installing necessary dependencies, 
creating a Docker image from source code, running the containerized application, and pushing the image to Docker Hub for future use.



Project description:

Set up an Amazon Linux EC2 instance and install Docker and Git.
Clone the source code from GitHub and create a Dockerfile.
Build and run the application inside a Docker container.
Expose the application via a public port and configure security groups.
Publish the Docker image to Docker Hub for easy access and deployment.


Project Steps

Steps 

1-	Create amazon Linux EC2 Instance and install git and docker
2-	Create working directory and clone the source code from GitHub
3-	Create the docker images through raw source code 
4-	Create and run the container with specific port and allow that port in Security group and publish web application.
5-	Create new repository on dockerhub and push new image to dockerhub



Step-1	Create amazon Linux EC2 Instance and install git and docker


Step-2	Create EC2 Instance Docker and Install Package git / Docker


step-3 Create working directory and clone the source code from GitHub

	

step-4 Create docker file in working directory with source code

vi Dockerfile

FROM nginx:alpine
COPY . /usr/share/nginx/html/			


step-5  Create the docker images through raw source code 
	docker build -t webapp .
	

step- 6  Create container and run container in specific port with respect to SG
	 docker run -d -p 8080:80 webapp


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




