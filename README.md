# Docker Essentials 
## Creating Docker Image of a SpringBoot Project
1. Makesure you have docker installed in your machine. If not, install it from [here](https://www.docker.com/)

2. First create a jar file of you project
   ```
    First go to "Maven" then select "your-project-name"
    Expand "Lifecycle"
    Do "clean"
    Then "install"
    This will create a jar file in your "target" folder
   ```
    
3. Add this file in your project's root directory and name it "Dockerfile"
   
    ```
    # Use an official OpenJDK runtime as a parent image
    FROM openjdk:17-jdk-alpine

    # Set the working directory in the container
    WORKDIR /app

    # Copy the executable jar file from your local machine to the container
    COPY target/your-spring-boot-app.jar app.jar

    # Expose the port the application will run on
    EXPOSE 8080

    # Run the jar file
    ENTRYPOINT ["java","-jar","app.jar"]
    ```

3. Start you docker server and run this command from your project's root directory

   ```
   docker build -t your-image-name .
   ```

## Docker Essential Commands
- Create docker image of your project
  
  ```
  docker build -t your-image-name .
  ```
- Run docker container
  
  ```
  docker run -p 8000:8080 your-image-name
  ```
- Stop docker container
  
  ```
  docker stop container-id
  ```
- See all docker images
  
  ```
  docker images
  ```
- List all docker containers
  
  ```
  docker container ls
  ```
- log into docker hub
  
  ```
  docker login
  ```
  
- create tag of existing docker image

  ```
  docker tag docker-image-name docker-hub-id/docker-image-name
  ```
  
- push docker image into dockerhub

  ```
  docker push docker-hub-id/docker-image-name
  ```
- pull docker image into local docker desktop

  ```
  docker pull docker-container-name
  ```
