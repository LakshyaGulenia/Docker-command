
# Docker Command Guide

## Creating and Managing Files and Containers

### Create a File in a Folder
To create a file in a folder:
```bash
touch <file_name>
```

### Check Docker Images on Local Ubuntu
To list all Docker images on your local machine:
```bash
sudo docker images
```

### Remove a Docker Image
To delete an image:
```bash
sudo docker rmi <image_name>
```

### Remove a Docker Container
To delete a container:
```bash
sudo docker rm <container_name>
```

### Check Running and Stopped Containers
To see all currently running and stopped containers:
```bash
sudo docker ps -a
```

### Check Modified Files in a Container
To check the history of modified files in a container:
```bash
docker diff <container_name>
```
This command shows what has been changed after the container was created.

### Create an Image from a Container
To create a new image from an existing container:
```bash
sudo docker commit <container_name> <new_image_name>
```

## Creating a Dockerfile

### Steps to Create a Dockerfile
1. Open a new Dockerfile using `vi`:
    ```bash
    vi Dockerfile
    ```
2. Press `i` to enter insert mode and write the following content:
    ```Dockerfile
    FROM ubuntu
    RUN echo "Your text here" > /tmp/testfile
    ```
3. To save and exit the file, press `Esc` and then type `:wq`.

### Create an Image from the Dockerfile
To build an image from the Dockerfile:
```bash
sudo docker build -t <image_name> .
```

## Creating and Running Containers

### Create a Container from an Image
To create and start a container from an image:
```bash
sudo docker run -it --name <container_name> <image_name> /bin/bash
```

### Check Files Inside a Container
Once inside the container:
- To list files in the current directory:
    ```bash
    ls
    ```
- To list files in the `/tmp` folder:
    ```bash
    ls /tmp
    ```
- To check the contents of a file (e.g., `testfile`):
    ```bash
    cat /tmp/testfile
    ```
