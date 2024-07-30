# Docker 
 for strarting you shoud check this link:    
 
 guiding for installing             
 https://developersho.com/blog/install-docker-desktop-on-windows                
 https://developersho.com/blog/how-to-install-windows-subsystem-for-linux-on-windows              
(the link for download in includid)               

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

*************************************
## Learing

in english :  
https://docker-curriculum.com/
https://www.tutorialspoint.com/docker/docker_installation.htm

in persian :        
https://tosinso.com/courses/docker-virtualization-step-by-step

if you wan to get help paste this in cmd :       
 
  docker run --help


### Listing all Docker Containers

 docker ps      
 docker ps -a
 docker ps --all

docker ps shows all containers that is running , of not runnning it will not show that 
You can use the -a or --all flag to show all containers, including stopped ones,                 
as it only shows running containers by default.                               
It returns an empty list if no containers are in use.                   



### Running a Docker Container
docker run -d -p (host port):(container port) (image name)              

 docker run -d -p 8080:80 nginx ((-d) creates a new container based on the image and runs it in the background)

you create the container by using that on the image
If the image isn't already available locally,
Docker pulls it from a registry when you run this command (if not jut after that press enter)               

### Stopping a Docker Container                   
docker stop (container name or container ID)              

docker stop my_container                
docker stop 39e6ae659d8f

### Pausing a Running Container

docker pause (container name or container ID)              

docker pause my_container      
docker pause 39e6ae659d8f                             

This command stops the container "my_container" or 39e6ae659d8f from running.                                
The container uses no CPU or memory when it is paused because its processes are frozen. The container does,                  
however, keep its resource allocation and configuration settings.


### Resuming a Docker Container        
docker unpause (paused container name or paused container ID)
 
docker unpause my_container                            
docker unpause 39e6ae659d8f                   

The above command resumes the paused container
When a container is paused, its processes can be carried out again by using the docker unpause command. By using this command,           
the container returns to its initial state and undoes the effects of the docker pause command.


### Restarting a Container

docker restart (container name or container ID)     

docker restart my_container           
docker restart 39e6ae659d8f          

 It is frequently used to force a container to reinitialize                    
 after experiencing problems or to apply changes to the configuration of a running container.               
 This command pauses and then resumes the execution of the container.
 The processes inside the container are stopped and then restarted upon restarting, enabling any modifications to take effect.

 ### Executing Commands in a Running Docker Container                   
docker exec -it (container name or container ID) bash       

docker exec -it my_container bash         
docker exec -it jovial_cray bash 

 

### Removing a Docker Container

 docker rm (stopped  container name or stopped  container ID)                    
     
 docker rm my_container          
 
You cannot remove a running container by this command
To remove a Docker container or containers, you can use the docker rm command. The container(s) whose ID or name you wish to remove can 
 be specified. 
This command only removes stopped containers by default;         
to forcefully remove running containers, you can use the -f or --force flag.

 docker rm (stopped  container name or stopped  container ID) -f                   
 docker rm my_container -f                   

 docker rm (stopped  container name or stopped  container ID) --force                          
 docker rm my_container --force                


### removing all stopped docker container 

docker container prune

To clear up disk space on the Docker host, you can use the docker container prune command to remove all stopped containers.         
It is a practical method of clearing out empty containers and recovering resources.            
for forcly removing :                 

docker container prune -f           
docker container prune --force

