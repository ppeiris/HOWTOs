# Introduction to docker

## Docker Image: 

- Image contain everything your service need to run (this is like a class in a programing language)
- Docker is based on Open standards (run on all the major linux standards)

## Docker Container: 

- Running instance of a Docker Image (this is like an instance of a class)
- Containers share the host operating systems kernel and resouce isolation is done using **_cgroups_** 
- Boot really fast compare to Virtual Machines (VMs)
- Does not take any disk space (this is running on the memory)
- Containers are secure since they are isolated

![docker](img/dcontainer.png)


## Benifits of using Docker 

- Application is backed into a image and can start within miliseconds
- New developers can star the env really quickly instead of installing and configuring enviornments
- Can experiment with new env and languages quickly 
- Since everything is packaged, corss env consistancy guranteeds
- Docker is a framework
- Docker images can be distributed publically
    - https://hub.docker.com/ contain many publically shared docker images 


## Download and run a docker image from docker hub (https://hub.docker.com/)

### busybox example:

- Docker can download and run pubilc images. The following command download the busybox docker latest image and run the echo command. 
    - ```--rm``` flag remove the docker container after it ran

![busybox](img/docker_busybox.png)

- Display all locally installed docker images 

![dockerimages](img/dockerimages.png)

- Dispaly all the Docker Containers 
    - when run without the ```--rm``` flag, the container stay in the memory 

![dockerps](img/dockerps.png)

- Manually remove the Docker Contianers from the memory
    - Use the containerID to remove from the memmory

![dockerrm](img/dockerrm.png)


##  Take a look at inside of a docker image
Take a look at the busybox docker image.

- ```-it``` flag: interactively 

![busyboxinside](img/busyboxinside.png)

- Remove docker images 
""
![dockerimr](img/dockerimr.png)

## Create Docker image form a container 

Lets run a Docker image. This time lets use the ubuntu docker image. This will download the docker ubuntu image and run it.

```
$ docker run -ti --rm ununtu
```

![dockerrunubuntu](img/dockerrunubuntu.png)
