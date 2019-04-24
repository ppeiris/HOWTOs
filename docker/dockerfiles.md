# Dockerfile


- Dockerfile name is `Dockerfile`
- Small program that create an image. 
- Dockerfiles are not shell scripts.
- Process you start on one line will not be running on the next line. 
- Environment variables you set will be set on the next line 
    - if you use ENV command, remember that each line is its own call to docker run

Run docker build command 

```
$docker build -t name_of_result .
```

- Docker skips lines that have not changed since the last build

## Create a docker image using Dockerfile

- Generate a simple and basic Dockerfile to load debian and then install vim

```
FROM debian:sid
RUN apt-get -y update # run the command through command line
RUN apt-get -y vim
CMD ["/bin/vim", "/tmp/notes"] # add entry point to the container
```

- Build the image

```
$ docker build -t IMAGE_NAME .
```

- `docker ps -a` show the new docker image

### Generate a docker image from another image

- Build a new image from a previous image (IMAGE_NAME)
- Add a file name `notes.txt` (from local machine) to `/tmp/notes.txt` (docker vm)
- fun command `CMD` to run a command 

```
FROM IMAGE_NAME
ADD notes.txt /tmp/notes.txt # add files 
ENV DB_HOST=env_name # add enviornment name and value
CMD ["/usr/bin/vim", "/tmp/notes.txt"]
```

# Multiproject Dockerfiles 

- Start the build using Debian (size if large)
- Convert to Apline linux as the final os

```
# Download debain and install it
FROM debian:sid as main_builder
RUN apt-get -y update # run the command through command line
RUN apt-get -y vim
ADD notes.txt /tmp/notes.txt # add files 
RUN cat /tmp/notes.txt |  wc -c > note_size.txt

# build the final package using Linux Apline 
# The final image we get is an Alpine image not a debian
FROM alpine
COPY --from=main_builder /note_size.txt /note_size.txt
ENTRYPOINT echo size of the file is; cat note_size.txt
```



# Besst Practice

- Start with generic image and start build the image you want using Dockerfiles 
- Do NOT override existing containers with new ones. Instead, build from dockerfiles
