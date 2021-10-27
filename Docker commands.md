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