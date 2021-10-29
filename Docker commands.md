#### Run a new container
1. Start new container from image
    ```
    docker run IMAGE
    docker run nginx
    ```

2. Assign the container a name while running
    ```
    docker run --name CONTAINER IMAGE
    docker run --name web nginx
    ```

3. Map a port while running
    ```
    docker run -p HOSTPORT:CONTAINERPORT IMAGE
    docker run -p 8080:80 nginx
    ```

4. Map all port while running
    ```
    docker run -P IMAGE
    docker run -P nginx
    ```

5. Start container in background
   ```
   docker run -d IMAGE
   docker run -d nginx
   ```

6. Assign a hostname
   ```
   docker run --hostname HOSTNAME IMAGE
   docker run --hostname srv nginx
   ```

7. Add a dns entry
   ```
   docker run --add-host HOSTNAME:IP IMAGE
   ```

8. Map a local directory into the container
   ```
   docker run -v HOSTDIR:TARGETDIR IMAGE
   docker run -v ~/:/usr/share/nginx/html nginx
   ```

9. Change the entrypoint
   ```
   docker run -it --entrypoint EXECUTABLE IMAGE
   docker run -it --entrypoint bash nginx
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

#### Managing conainters
1. Show a list of running containers
   ```
   docker ps
   ```
2. Show a list of all containers
   ```
   docker ps -a
   ```
3. Delete a container
   ```
   docker rm CONTAINER
   docker rm web
   ```
4. Delete a running container
   ```
   docker rm -f CONTAINER
   docker rm -f web
   ```
5. Delete stopped containers
   ```
   docker container prune
   ```
6. Stop a running container
   ```
   docker stop CONTAINER
   docker stop web
   ```
7. Start a stopped container
   ```
   docker start CONTAINER
   docker start web
   ```
8. Copy a file from a container to the host
   ```
   docker cp CONTAINER:SOURCE TARGET
   docker cp web:/index.html index.html
   ```
9. Copy a file from the host to the container
   ```
   docker cp TARGET CONTAINER:SOURCE
   docker cp index.html web:/index.html
   ```
10. Start a shell inside a running container
   ```
   docker exec -it CONTAINER EXECUTABLE
   docker exec -it web bash
   ```
11. Rename a container
   ```
   docker rename OLD_NAME NEW_NAME
   docker rename 096 web
   ```
12. Create an image out of container
   ```
   docker commit CONTAINER
   docker commit web
   ```

#### Info & Stats
1. Show the logs of a container
   ```
   docker logs CONTAINER
   docker logs web
   ```
2. Show stats of running container
   ```
   docker stats
   ```
3. Show processes of container
   ```
   docker top CONTAINER
   docker top web
   ```
4. Show installed docker version
   ```
   docker version
   ```
5. Get detailed info about an object
   ```
   docker inspect NAME
   docker inspect nginx
   ```
6. Show all modified files in container
   ```
   docker diff CONTAINER
   docker diff web
   ```
7. Show mapped ports of a container
   ```
   docker port CONTAINER
   docker port web
   ```

#### Manage Images
1. Download an image
   ```
   docker pull IMAGE[:TAG]
   docker pull nginx
   ```
2. Upload an image to a repository
   ```
   docker push IMAGE
   docker push myimaga:1.0
   ```
3. Delete an image
   ```
   docker rmi IMAGE
   ```
4. Show a list of all images
   ```
   docker images
   ```
5. Delete dangling images
   ```
   docker image prune
   ```
6. Delete all unused images
   ```
   docker image prune -a
   ```
7. Build an image from a Dockerfile
   ```
   docker build DIRECTORY
   docker build .
   ```
8. Tag an image
   ```
   docker tag IMAGE NEWIMAGE
   docker tag ubuntu ubuntu:18.04
   ```
9. Build and tag an image from a Dockerfile
   ```
   docker build -t IMAGE DIRECTORY
   docker build -t myimage
   ```
10. Save an image to tar file
   ```
   docker save IMAGE > FILE
   docker save nginx > nginx.tar
   ```
11. Load an image from a tar file
   ```
   docker load -i TARFILE
   docker load -i nginx.tar
   ```
