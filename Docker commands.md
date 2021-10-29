#### Run a new container
1. Start new container from image
    ```
    docker run IMAGE
    ```

2. Assign the container a name while running
    ```
    docker run --name CONTAINER IMAGE
    ```


#### Building a Docker image
1. Build an image from the Dockerfile in the current directory and tag the image
   ```
   docker build -t IMAGE
   ```
     
2. List all images that are locally stored with the Docker Engine
   ```
   docker image ls
   ```

3. Delete an image from the local image store
   ```
   docker image rm IMAGE
   ```


#### Sharing Docker images
1. Pull an image from a registry  
   ```
   docker pull myimage:1.0  
   ```
2. Retag a local image with a new image name and tag
   ```
   docker tag myimage:1.0 myrepo/myimage:2.0
   ```
  
3. Push an image to a registry 
   ```
   docker push myrepo/myimage:2.0
   ```
   
#### Running a Docker image
1. Run a container from the Alpine version 3.9 image, name the running container "web" and expose port 5000 externally, mapped port 80 inside the container
   ```
   docker container run --name web -p 5000:80 alpine:3.9
   ```
2. Stop a running container through SIGTERM
   ```
   docker container stop web
   ```
3. Stop a running container through SIGKILL
   ```
   docker container kill web
   ```
4. List the networks
   ```
   docker network ls
   ```
5. List the running containers (add --all to include stopped containers)
   ```
   docker container ls
   ```
6. Delete all running and stopped containers
   ```
   docker container rm -f $(docker ps -aq)
   ```
