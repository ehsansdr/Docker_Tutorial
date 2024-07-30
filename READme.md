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
docker stop (container name or container ID )              

docker stop my_container                
docker stop 39e6ae659d8f

### Pausing a Running Container

docker pause (container name or container ID )              

docker pause my_container      
docker pause 39e6ae659d8f                             

This command stops the container "my_container" or 39e6ae659d8f from running.                                
The container uses no CPU or memory when it is paused because its processes are frozen. The container does,                  
however, keep its resource allocation and configuration settings.



