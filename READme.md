# Docker 
 for strarting you shoud check this link:    
 
 guiding for installing             
 https://developersho.com/blog/install-docker-desktop-on-windows                
 https://developersho.com/blog/how-to-install-windows-subsystem-for-linux-on-windows              
(the link for download in included)               

or     
https://docs.docker.com/desktop/           

downloading Docker Desktop:                    
https://www.docker.com/products/docker-desktop/
or            
https://www.tutorialspoint.com/docker/docker_installation.html  

my docker hub dashboard :           
https://app.docker.com/
and the tutorial for the usinf hub :     
https://www.tutorialspoint.com/docker/docker_hub.htm

best extension for docker for programming:       
[top-docker-extensions-for-developers](https://digma.ai/top-docker-extensions-for-developers/#vulnerability-detection)

*************************************
## Learing
### **you can use intellij idea terminal** 
in english :  
https://docker-curriculum.com/
https://www.tutorialspoint.com/docker/docker_installation.htm

in persian :        
https://tosinso.com/courses/docker-virtualization-step-by-step

if you want to get help paste this in cmd :       
 
  docker run --help


### Listing all Docker Containers

 `docker ps`

 `docker ps -a` 

 `docker ps --all`

docker ps shows all containers that is running , of not runnning it will not show that 
You can use the -a or --all flag to show all containers, including stopped ones,                 
as it only shows running containers by default.                               
It returns an empty list if no containers are in use.                   



### Running a Docker Container
`docker run -d -p (host port):(container port) (image name) `             

 `docker run -d -p 8080:80 nginx` ((-d) creates a new container based on the image and runs it in the background)

you create the container by using that on the image
If the image isn't already available locally,
Docker pulls it from a registry when you run this command (if not jut after that press enter)               

### Stopping a Docker Container                   
`docker stop (container name or container ID)`              

`docker stop my_container` 

`docker stop 39e6ae659d8f`

### Pausing a Running Container

`docker pause (container name or container ID)`              

`docker pause my_container`   

`docker pause 39e6ae659d8f`                               

This command stops the container "my_container" or 39e6ae659d8f from running.                                
The container uses no CPU or memory when it is paused because its processes are frozen. The container does,                  
however, keep its resource allocation and configuration settings.


### Resuming a Docker Container        
`docker unpause (paused container name or paused container ID)`
 
`docker unpause my_container `  

`docker unpause 39e6ae659d8f`                   

The above command resumes the paused container
When a container is paused, its processes can be carried out again by using the docker unpause command. By using this command,           
the container returns to its initial state and undoes the effects of the docker pause command.

### running stopped container

`docker run -e (Stopped container name or ID) (image name)`

`docker run -e jovial_cray docker/getting-started`

### Restarting a Container

`docker restart (container name or container ID)`    

`docker restart my_container`     

`docker restart 39e6ae659d8f`          

 It is frequently used to force a container to reinitialize                    
 after experiencing problems or to apply changes to the configuration of a running container.               
 This command pauses and then resumes the execution of the container.
 The processes inside the container are stopped and then restarted upon restarting, enabling any modifications to take effect.

 ### Executing Commands in a Running Docker Container                   
`docker exec -it (container name or container ID) bash`       

`docker exec -it my_container bash`    

`docker exec -it jovial_cray bash` 

 

### Removing a Docker Container

 `docker rm (stopped  container name or stopped  container ID)`                    
     
 `docker rm my_container`          
 
You cannot remove a running container by this command
To remove a Docker container or containers, you can use the docker rm command. The container(s) whose ID or name you wish to remove can 
 be specified. 
This command only removes stopped containers by default;         
to forcefully remove running containers, you can use the -f or --force flag.

 `docker rm (stopped  container name or stopped  container ID) -f`                   
 `docker rm my_container -f`                   

 `docker rm (stopped  container name or stopped  container ID) --force`                          
 `docker rm my_container --force`                


### removing all stopped docker container 

`docker container prune`

To clear up disk space on the Docker host, you can use the docker container prune command to remove all stopped containers.         
It is a practical method of clearing out empty containers and recovering resources.            


for forcly removing :                 

`docker container prune -f`           
`docker container prune --force`

If you want to remove all Docker containers together, you can use a chain two commands               
- “docker ps -aq”   (return all containers)
 which is used to obtain a list of all container IDs and combine it with the “docker rm” command to remove all containers, including running containers.


`docker rm (docker ps -aq)` 

it will remove the out put of (docker ps -aq)


### getting docker version

`docker -v`

`docker --version`


### getting all installed images
``
`docker images`
If you want to just display the Image IDs, you can use the "–quiet" flag.

`docker image ls -q`

    PS C:\Java projects\Docker_Tutorial> docker image ls -q
    209ed7c86ebd
    90ec73daf8e7
    a72860cb95fd
    07a4ee949b9e
    cea77dc94bbc
    1a0fb356ea35
    d2c94e258dcb
    3597029f1608
    b08571911ecf



### Push Images from Docker Hub (private repo)

Before you push an image to Docker Hub, you should ensure that it is properly tagged with the repository name and version.

Here, we will use a "hello-world" image from the Docker Hub public repository for reference. You can tag an image using the following command −

`docker tag <image_id(the image you want to have same as that)> <username/repository_name:tag>`

`docker tag d2c94e258dcb iamrj888/myfirstrepo:v1`

creates a new tag for an existing Docker image. 
Tags allow you to label and reference multiple versions of an image.
This command is frequently used before uploading an image to a registry under a different tag.

 **repository name must be lowercase**

 **do not need to have github,you need the password you set in** docker hub **you will have identical image with the drfrent name**

###  Log in to Docker Hub

`docker login`

you need to enter username and password

go to [https://hub.docker.com/](https://hub.docker.com/) create account and then 
enter the username and pass word and wait

### Push the Image

you need to log in

Now that you have logged in,                 
you can use the docker push command to push the tagged image to Docker Hub.

`docker push <username/repository_name:tag>`

`docker push hello-world:latest`

`REPOSITORY                             TAG       IMAGE ID       CREATED         SIZE
 mochoa/pgadmin4-docker-extension       8.10.0    209ed7c86ebd   12 days ago     11.8MB
 dpage/pgadmin4                         8.10      90ec73daf8e7   12 days ago     481MB
 postgres                               latest    07a4ee949b9e   3 months ago    432MB
 snyk/snyk-docker-desktop-extension     0.9.0     cea77dc94bbc   3 months ago    83.7kB
 portainer/portainer-docker-extension   2.19.4    1a0fb356ea35   8 months ago    294MB
 hello-world                            latest    d2c94e258dcb   15 months ago   13.3kB
 ddosify/ddosify-docker-extension       0.2.3     3597029f1608   16 months ago   20.1MB
 jfrog/jfrog-docker-desktop-extension   1.2.1     b08571911ecf   23 months ago   83.4MB
`


You can verify the pushed image in the Docker Hub repositories.

### Pulling Images from Docker Hub

You can use the Docker pull command to pull the images from Docker Hub.

`docker pull <username/repository_name:tag>`

`docker pull hello-world:latest`


### Removing Docker Images

`docker rmi <repository_name:tag>`

`docker rmi myapp:latest`

    PS C:\Java projects\Docker_Tutorial> docker images
    REPOSITORY                             TAG       IMAGE ID       CREATED         SIZE
    ehsan/ehsan_repo                       latest    d2c94e258dcb   15 months ago   13.3kB
    PS C:\Java projects\Docker_Tutorial> docker rmi ehsan/ehsan_repo
    Untagged: ehsan/ehsan_repo:latest
 means : successful

The docker rmi command removes one or more Docker images from your local machine.
You can provide either the image name or the image ID.


### Pruning Docker Images
The docker image prune command removes unused Docker images from your local machine.                
This command is useful for freeing up disk space by removing images                  
that are no longer associated with any containers or tags.         

**Options** 

    -a, --all − Delete all unused images, not just the dangling ones.
    -f, --force − Don't ask for confirmation before cleaning.

    docker image prune -a

### Viewing Docker Image History                  
The docker image history command shows the history of a Docker image,          
including the commands and instructions used during the image-building process.         
This can be useful for determining how an image is formed and diagnosing problems.      

    docker image history <image name>:latest

    docker image history myimage:latest




docker image COMMAND

Manage images

Commands:              
  `build`       Build an image from a Dockerfile                      
  `history`     Show the history of an image                
  `import`      Import the contents from a tarball to create a filesystem image             
  `inspect`     Display detailed information on one or more images                 
  `load`        Load an image from a tar archive or STDIN                  
  `ls`          List images                  
  `prune`       Remove unused images            
  `pull`        Pull an image or a repository from a registry          
  `push`        Push an image or a repository to a registry           
  `rm`          Remove one or more images                
  `save`        Save one or more images to a tar archive (streamed to STDOUT by default)            
  `tag`         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE                  

********************

for creating postgres container:

    docker run -d -e POSTGRES_USERNAME=postges -e POSTGRES_PASSWORD=postgres -p 5432:5432 postgres
