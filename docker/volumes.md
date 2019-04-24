# Docker Volumes

- Volumes are virtual "disks" to store and share data
- Data in a volume is not a part of the image (its local data)



## Docker had two types of Volumes 



### Persistant Volumes
- Created in host machine 
- Volume exists after container get deleted 


### Ephemeral Volumes
- Volume exists until a container uses them. 
- Volume disappear when no container uses it.


## Sharing data between host and container 

### share a folder with a container 

- `-v` argument indicate Volume

```bash
$ docker run -ti -v /host/dir/path:/container/dir/path CONTAINER_ID bash 
```

### share a single file with a container

 - This is same as sharing a dir, but make sure to have the file in host machine before start the container, otherwise it will create a directory

### Share directory amoung containers 

- Create a dir in the container 

```
$ docker run -it --name CONTAINER_1 -v /data_dir ubuntu bash 
```

- Create another docker container and mount the `/data_dir` from CONTAINER_1 to new container 
```
$ docker run -it --name CONTAINER_2 --volumes-from CONTAINER_1 ubuntu bash 
```

- We can add `/data_dir` from CONTAINER_1 to any container using above command. This `/data_dir` folder will live and persist data until all the containers exit. 
