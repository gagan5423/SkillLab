Session 4

docker:

what is dev environment?  
It is a server where we are able to run our application.

testing environment?  
Where software testing team can perform the functional test cases, non-functional test cases, performance testing, load testing. All test cases will run in this environment.

uat environment:  
Before releasing the product into the market, we have to show prototype of the application to the client.

production environment:  
Where we actually deploy the application and users can access it.

what is meant by container?  
Container is a virtual machine where you are actually going to run the application.

docker file is a text document that contains a set of instructions on how to run the application in the container.  
Docker file is used to create a docker image.

docker image is a template that contains what you need to run the application. It includes source code, dependencies, config files, library files, and the platform you want to run the application on (build once, run anywhere).

what is docker hub?  
Docker hub is a registry or library where we can store all the docker images.

what are daemon containers or detached mode?  
Running containers in the background without attaching to them.

Every microservice works on different port numbers.

steps:  
1. Create an EC2 instance  
2. Create a key-pair  
3. Edit security group with your name  
4. Open Putty and connect to the instance  
5. In Putty terminal: sudo su  
6. Check Docker status: service docker status  
7. Start Docker: service docker start  
8. Create a Docker container  

commands:  
- docker ps -a : shows all docker containers, regardless of state  
- docker ps : shows only running containers  
- ctrl + p + q : detach from container without stopping it  
- -p : specify port number  
- host port number: user-defined, used to access application from server  

after creating a container:  
- Go to AWS, click instance ID  
- Copy public IP address, paste in browser  
- Go to Security -> Edit Inbound Rules -> Add All TCP -> Anywhere IPv4 -> Done

docker file instructions:  
1. from : defines base image or parent image  
2. copy : copy file or directory from local to docker image  
3. add : same as copy, can download packages from internet  
4. run : install packages or dependencies in container  
5. .dockerignore : exclude unnecessary files while building image  
6. cmd : defines the code/artifact to run in container (allows runtime arguments)  
7. entrypoint : defines the entry of the application (does not allow runtime arguments)  
8. expose : defines the port number for application access  
9. env : defines environment variables  
10. workdir : sets working directory in container  
11. user : create user accounts inside container

workflow:  
1. Fork the repository  
2. Clone to local machine  
3. Open terminal  
4. git clone -b master https://github.com/gagan5423/Dimple-CapsuleProject.git  
5. On the server, clone the repo  
6. Go inside the repo  
7. Build docker image  
8. Push to Docker Hub  

notes:  
- As a DevOps engineer, collect endpoint, port numbers, and environment variables  
- Match container port number with application port (defined in .env file)  
- When writing Docker file, follow these six steps:  
  - Identify base image  
  - Create work directory  
  - Copy dependencies  
  - Install dependencies  
  - Copy source code  
  - Define expose port number  
  - Mention the code to run in container

assignment for tomorrow:  
[assignment content not provided]